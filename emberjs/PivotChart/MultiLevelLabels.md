---
layout: post
title: Multi-level Labels
description: multilevellabels
platform: emberjs
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# Multi-level Labels

Multi-level labels allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the expander present in the OlapChart. You can enable the option by setting the property `e-enableMultiLevelLabels` as **“true”.**

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotchart id="PivotChart" e-enableMultiLevelLabels=model.enableMultiLevelLabels }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                enableMultiLevelLabels: true
        }
    }
});

{% endhighlight %}


## Relational

![](MultiLevelLabels_images/relational.png)

## OLAP

![](MultiLevelLabels_images/olap.png)

