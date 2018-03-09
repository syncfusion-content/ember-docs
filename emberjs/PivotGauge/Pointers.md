---
layout: post
title: Pointers
description: pointers
platform: emberjs
control: PivotGauge
documentation: ug
---

# Pointers

## Pointer Types

PivotGauge pointers has two types such as,

* Needle
* Marker

Needle type pointers are the default pointers which is always located at the center of the Gauge. Following shapes that are supported for the needle pointers are:

* Rectangle
* Triangle
* Trapezoid
* Arrow
* Image.

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            scales: [{
                //...
                pointers: [{
                    type: "needle",
                    needleType: "trapezoid",
                }]
            }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/NeedlePointer.png) 

For marker pointer, the available shapes are Rectangle, Triangle, Ellipse, Diamond, Pentagon, Circle, Slider, Pointer, Wedge, Trapezoid, RoundedRectangle and Image.

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
            scales: [{
                //...
                pointers: [{
                    type: "marker",
                    markerType: "diamond",
                }]
            }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/MarkerPointer.png) 

## Adding Pointer Collection

Pointer collection can be directly added to the scales option within the PivotGauge control. 

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
    scales: [{
            //...
            pointers: [
                {
                    type: "needle",
                    needleType: "triangle",
                }, 
                {
                    type: "marker",
                    markerType: "diamond"
                }     
            ]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/PointerCollection.png) 

## Appearance Customization

The appearance of the pointer can be customized through the following properties.

* **Border** – sets the "Color" and "Width" of the pointer border.
* **BackgroundColor** – sets the background color of the pointer.
* **Length** – sets the length of the pointer.
* **Width** – sets the width of the pointer.
* **Opacity** – sets the opacity of the pointer.  By default, the value is 1.
* **Type** – sets the type of the pointer.  By default, the type is "Needle".

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
    scales: [{
            //...
            pointers: [
                {
                    border: {
                        color: "green",
                        width: 2
                    },
                    backgroundColor: "yellow",
                    length: 120,
                    width: 7,
                    opacity: 0.6,
                    type: "needle",
                    needleType: "triangle"
                }, 
                {
                    border: {
                        color: "green",
                        width: 2
                    },
                    backgroundColor: "yellow",
                    length: 25,
                    width: 15,
                    opacity: 0.8,
                    type: "marker",
                    markerType: "diamond"
                }
            ]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/AppearanceCustomization.png) 

## Pointer Position

Pointer can be positioned with the help of below two properties.

* **DistanceFromScale** -  defines the distance between scale and pointer. By default, the value is 0.
* **Placement** -  defines the location of the pointer. By default, the value is "Center".

N> Both the properties can be applied only if the pointer type is set to “Marker”. Needle pointer type appears only at the center of the control, which is its default position.

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
    scales: [{
            //...
            pointers: [{
                //...
                type: "marker",
                placement: "far",
                distanceFromScale: 2
            }]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/PointerPosition.png) 

## Pointer Image

It is possible to replace the pointers with image. To view the pointers as image, we need to set the appropriate location in the `ImageUrl` property.

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
    scales: [{
            //...
            pointers: [{
                //For replacing needle pointer with image
                type: "needle",
                needleType: "image",
                imageUrl: "image.png"
            }, 
            {
                //For replacing marker pointer with image
                type: "marker",
                markerType: "image",
                imageUrl: "image.png"
            }]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/MarkerPointerWithImage.png)

## Pointer Value Text

To display the current value of the pointers in PivotGauge control, **"PointerValueText"** option inside pointers is used.  Following are the properties used to enable and customize the pointer value text.
 
* **ShowValue** – enables the pointer value text by setting the property to "true". By default, its value is "true".
* **Distance** – sets the distance between pointer and text.
* **Color** – sets the color of the text.
* **Opacity** – sets the opacity of the text. By default, its value is 1.
* **Angle** – sets the rotation angle of the text. By default, its value is 0.
* **Font** – sets the font size, font style and font family of the text.

{% highlight html %}

	{% raw%}
	{{ej-pivotgauge id="PivotGauge" e-scales=model.scales }}
    {% endraw%}

{% endhighlight %}

{% highlight javascript %}

import Ember from 'ember';

export default Ember.Route.extend({
   model(){
    return {
    scales: [{
            //...
            pointers: [{
                //For needle type
                pointerValueText: {
                    showValue: true,
                    distance: 10,
                    color: "red",
                    opacity: 0.7,
                    angle: 20,
                    font: {
                        size: "15px",
                        fontStyle: "Normal",
                        fontFamily: "Arial"
                    }
                }
            }, 
            {
                //For marker type
                pointerValueText: {
                    showValue: true,
                    distance: 40,
                    color: "red",
                    opacity: 0.7,
                    angle: -40,
                    font: {
                        size: "15px",
                        fontStyle: "Normal",
                        fontFamily: "Arial"
                    }
                },
            }]
        }]
        }
    },
});
    
{% endhighlight %}

![](Pointers_images/PointerValueText.png) 
