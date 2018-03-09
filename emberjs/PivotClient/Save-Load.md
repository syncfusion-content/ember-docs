---
layout: post
title: Save and Load Report
description: save and load report
platform: emberjs
control: pivotclient
documentation: ug
keywords: ejpivotclient, pivotclient, pivotclient widget, js pivotclient 
---

# Save and Load Report

Save and load report allows you to save the current report collection of PivotClient and render the control later on loading the same.

## Save Report to Local Storage

We can store the report collection of PivotClient to local storage, by setting the `e-enableLocalStorage` property to true and by defining the `e-saveReport` event of PivotClient.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotclient id="PivotClient" e-enableLocalStorage=model.enableLocalStorage e-saveReport=model.saveReport}}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            //...
            
            enableLocalStorage: true,
            saveReport: function (args) {
                    var reportCollection = [];
                    if ((localStorage.pivotClientRPTCollection != "" && !ej.isNullOrUndefined(localStorage.pivotClientRPTCollection))) {
                        reportCollection = JSON.parse(localStorage.pivotClientRPTCollection);
                    }
                    if(args.saveReportSettings) {
                        reportCollection.push(({ reportName: args.saveReportSetting.reportName, reportCol: args.saveReportSetting.reportCollection }));
                        localStorage.pivotClientRPTCollection = JSON.stringify(reportCollection);
                    }
            }
        }
    }
});

{% endhighlight %}

## Load Report from Local Storage

We can load the stored report collection of PivotClient from local storage, by setting the `e-enableLocalStorage` property to true and using the `e-LoadReport` and `e-FetchReport` events in PivotClient.

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotclient id="PivotClient" e-enableLocalStorage=model.enableLocalStorage e-loadReport=model.loadReport}}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            //...
            
            enableLocalStorage: true,
            loadReport: function (args) {
                    var reportCollection = [];
                    if ((localStorage.pivotClientRPTCollection != "" && !ej.isNullOrUndefined(localStorage.pivotClientRPTCollection))) {
                        reportCollection = JSON.parse(localStorage.pivotClientRPTCollection);
                    }
                    if (args.fetchReportSetting) 
                        args.fetchReportSetting.reportList = $.map(reportCollection, function (item, index) { return item.reportName; }).join("__");
                    else if (args.loadReportSetting) 
                        args.loadReportSetting.reportCollection = $.map(reportCollection, function (item, index) { if (item.reportName == args.loadReportSetting.selectedReport) return item.reportCol; });
                    }
            }
        }
    }
});

{% endhighlight %}