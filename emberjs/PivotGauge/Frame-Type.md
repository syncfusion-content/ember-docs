---
layout: post
title: Frame Type
description: frame type 
platform: emberjs
control: PivotGauge
documentation: ug
---

# Frame Type

## Full Circle

Full Circle frame lets the PivotGauge display in circular shape. Frame type can be set using the `frameType` property.  By default, the frame type is "fullcircle".

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-frame=model.frame }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            frame: { 
                frameType: "fullcircle" 
            }
        }
    },
});
    
{% endhighlight %}

![](Frame-Type_images/FullCircle.png)

## Half Circle
Half Circle frame lets the PivotGauge to display in semi-circular shape. For this, frame type needs to be set as "HalfCircle" within the `frameType` property and need to set `startAngle` and `sweepAngle` for the PivotGauge in the `scales` property.


{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-frame=model.frame e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            frame: {
               frameType: 'halfcircle',
               halfCircleFrameStartAngle: 180, halfCircleFrameEndAngle: 360
        },
        scales: [{
                    //..
                    startAngle: 180, sweepAngle: 180
                    //..
                }]
        }
    },
});
    
{% endhighlight %}

![](Frame-Type_images/HalfCircle.png)
