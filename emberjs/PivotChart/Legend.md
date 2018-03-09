---
layout: post
title: Legend
description: legend
platform: emberjs
control: PivotChart
documentation: ug
keywords: ejpivotchart, pivotchart, js pivotchart
---

# Legend

## Legend Visibility

You can enable or disable legend using the `visible` property inside the `legend` object.

N> By default, the legend is visible in PivotChart.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	{{ej-pivotchart id="PivotChart" e-legend=model.legend }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                legend: {
					visible: true
				},
        }
    }
});

{% endhighlight %}

{% endtabs %}

![](Legend_images/Legend_img1.png) 

## Legend Shape

You can customize the legend `shape` in PivotChart control. Default value of legend shape is “rectangle”. Following legend shapes that are supported:

* rectangle
* circle
* cross
* diamond
* pentagon
* hexagon
* star
* ellipse
* triangle etc.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                legend: {
					visible: true, 
                    shape: "Star" 
				},
        }
    }
});

{% endhighlight %}

![](Legend_images/Legend_img2.png) 

## Legend Position

By using the `position` property, you can place the legend at top, bottom, left or right of the PivotChart. 

N> Default value of legend position is "bottom" in PivotChart.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                legend: {
					visible: true, 
                    shape: "Star", 
                    position: "top"
				},
        }
    }
});

{% endhighlight %}

![](Legend_images/Legend_img3.png) 

## Legend Title

To add the legend title, you have to specify the title text in `title.text` property.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                legend: {
					visible: true, 
                    title:{ text: "Countries" }
				},
        }
    }
});

{% endhighlight %}

![](Legend_images/Legend_img4.png) 

## Legend Alignment

You can align the legend to center, far and near based on its position in the Chart area using the `alignment` option.
 
{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                legend: {
					visible: true, 
                    alignment: "Near"
				},
        }
    }
});

{% endhighlight %}

![](Legend_images/Legend_img5.png)

## Legend Items - Size and Border

By using the legend `itemStyle.width`, `itemStyle.height` and `itemStyle.border` properties, you can change the legend items - size and border.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                legend: {
					visible: true,
                    itemStyle:
                    {
                        height: 12,
                        width: 12,
                        border:
                        {
                            color: 'magenta',
                            width: 1.5
                        }
                    } 
				},
        }
    }
});

{% endhighlight %}

![](Legend_images/Legend_img6.png)
 
## Legend Border

By using the `border` option in legend, you can customize border color and width.

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                legend: {
					visible: true, 
                    border:{
                        color: "#FFC342",
                        width: 2
                    }
				},
        }
    }
});

{% endhighlight %}

![](Legend_images/Legend_img7.png)

## Legend Text

By using the `font` option, you can customize the font family, font style, font weight and size of the legend text. 

{% highlight js %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
                //...
                
                legend: {
					visible: true, 
                    font:
                    {
                        fontFamily: 'Segoe UI',
                        fontStyle: 'italic',
                        fontWeight: 'bold',
                        size: '13px'
                    }
				},
        }
    }
});

{% endhighlight %}

![](Legend_images/Legend_img8.png)