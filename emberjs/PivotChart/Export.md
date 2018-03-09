---
layout: post
title: Export
description: export
platform: emberjs
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# Exporting

The PivotChart control can be exported to the following file formats.

* Excel
* Word
* PDF
* Image

The PivotChart control can be exported by invoking **“exportPivotChart”** method, with an appropriate export option as parameter.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotchart id="PivotChart" e-commonSeriesOptions=model.commonSeriesOptions }}
    {{ej-button id="Export" e-text="Export" e-click=model.Export }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                commonSeriesOptions: {
					type: ej.PivotChart.ChartTypes.Column
				},
                Export: function(args) {
                    var chartObj = $('.e-pivotchart').data("ejPivotChart");
                    chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/ExcelExport","fileName");
                }
        }
    }
});

{% endhighlight %}

{% endtabs %}

## Excel Export

User can export contents of the PivotChart to Excel document for future archival, references and analysis purposes.

To achieve Excel export, service URL and file name is sent as the parameter.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var chartObj = $('.e-pivotchart').data("ejPivotChart");
                    chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/ExcelExport","fileName");
                }
        }
    }
});

{% endhighlight %}

## Word Export

User can export contents of the PivotChart to Word document for future archival, references and analysis purposes.

To achieve Word export, service URL and file name is sent as the parameter.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var chartObj = $('.e-pivotchart').data("ejPivotChart");
                    chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/WordExport","fileName");
                }
        }
    }
});

{% endhighlight %}

## PDF Export

User can export contents of the PivotChart to PDF document for future archival, references and analysis purposes.

To achieve PDF export, service URL and file name is sent as the parameter.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var chartObj = $('.e-pivotchart').data("ejPivotChart");
                    chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/PDFExport","fileName");
                }
        }
    }
});

{% endhighlight %}

## Image Export

User can export contents of the PivotChart to image format for future archival, references and analysis purposes. We can export PivotChart to the following image formats.

* PNG
* EMF
* JPG
* GIF
* BMP

To export PivotChart in PNG format, service URL, file name and **“ej.PivotChart.ExportOptions.PNG”** enumeration value is sent as the parameter. This is similar to other image formats.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                Export: function(args) {
                    var chartObj = $('.e-pivotchart').data("ejPivotChart");
                    chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/ImageExport","fileName","png");
                }
        }
    }
});

{% endhighlight %}

## Exporting Customization

You can add title and description to the exporting document by using title and description property obtained in the "e-beforeExport" event.

N> Title and description cannot be added to image formats.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotchart id="PivotChart" e-commonSeriesOptions=model.commonSeriesOptions e-beforeExport=model.beforeExport}}
    {{ej-button id="Export" e-text="Export" e-click=model.Export }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                commonSeriesOptions: {
					type: ej.PivotChart.ChartTypes.Column
				},
                Export: function(args) {
                    var chartObj = $('.e-pivotchart').data("ejPivotChart");
                    chartObj.exportPivotChart("http://js.syncfusion.com/ejservices/api/PivotChart/Olap/ExcelExport","fileName");
                },
                beforeExport: function(args) {
                    args.title = "PivotChart";
                    args.description = "Visualizes both OLAP and Relational datasource in graphical format";
                }
        }
    }
});

{% endhighlight %}

{% endtabs %}

The below screenshot shows the PivotChart control exported to Excel document.

![](Export_images/Export_ExcelClient.png)

The below screenshot shows the PivotChart control exported to Word document.

![](Export_images/Export_WordClient.png)

The below screenshot shows the PivotChart control exported to PDF document.

![](Export_images/Export_PDFClient.png)

The below screenshot shows the PivotChart control exported to PNG format.

![](Export_images/Export_PNGClient.png)