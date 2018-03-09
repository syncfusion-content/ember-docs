---
layout: post
title: Paging
description: paging
platform: emberjs
control: PivotGrid
documentation: ug
keywords: ejpivotgrid, pivotgrid, js pivotgrid
---

# Paging

## Pager 

Paging helps to improve the rendering performance of the PivotGrid control by dividing large amount of data into sections and displaying one section at a time. You can enable Paging option in PivotGrid by setting the `e-enablePaging` property to true. You can provide the page size and current page details for each axis in `pagerOptions` property.

In-order to initialize a **Pager**, first you need to define a **div** tag with an appropriate **id** attribute which acts as a container for the widget. Then you need to initialize the widget using **ejPivotPager** method.

Inside the **ejPivotPager** method, the enumeration property mode needs to be set to **ej.PivotPager.Mode.Both** in-order to display both categorical pager and series pager. The other enumerations such as **ej.PivotPager.Mode.Categorical** and **ej.PivotPager.Mode.Series** will display only categorical pager and series pager respectively.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	<!--Create a tag which acts as a container for PivotGrid-->
	{{ej-pivotgrid id="PivotGrid" e-dataSource=model.dataSource e-enablePaging=model.enablePaging }}
	<!--Create a tag which acts as a container for Pager. -->
	{{ej-pivotpager id="PivotPager1" e-targetControlID=model.targetControlID }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
                dataSource: {
                data: "http://bi.syncfusion.com/olap/msmdpump.dll", //data
                catalog: "Adventure Works DW 2008 SE",
                cube: "Adventure Works",
                rows: [
                    {
                        fieldName: "[Date].[Fiscal]"
                    }
                ],
                columns: [
                    {
                        fieldName: "[Customer].[Customer Geography]"
                    }
                ],
                values: [
                    {
                        measures: [
                            {
                                fieldName: "[Measures].[Internet Sales Amount]",
                            }
                        ],
                        axis: "columns"
                    }
                ],
                pagerOptions : {
                    categoricalPageSize: 3,
                    seriesPageSize: 3,
                    categoricalCurrentPage: 1,
                    seriesCurrentPage: 1
                }
            },
			targetControlID: "PivotGrid",
            enablePaging: true
           }
        }
    });
{% endhighlight %}

{% endtabs %}

Following are the navigation options available in Pager.

* Move First - Navigates to the first page.
* Move Last - Navigates to the last page. 
* Move Previous - Navigates to the previous page from the current page.
* Move Next - Navigates to the next page from the current page.
* Numeric Box - Navigates to the desired page by entering an appropriate page number in numeric value.

![](Paging_images/paging.png)


## Virtual Scrolling

Virtual Scrolling is a technique that allows user to view the PivotGrid information page by page with the use of vertical and horizontal scrollbar. You can enable Virtual Scrolling option in PivotGrid by setting the `e-enableVirtualScrolling` property to true. You can provide the page size and current page details for each axis in `pagerOptions` property. 

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	<!--Create a tag which acts as a container for PivotGrid-->
	{{ej-pivotgrid id="PivotGrid" e-dataSource=model.dataSource e-enableVirtualScrolling=model.enableVirtualScrolling }}}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
                dataSource: {
                data: "http://bi.syncfusion.com/olap/msmdpump.dll", //data
                catalog: "Adventure Works DW 2008 SE",
                cube: "Adventure Works",
                rows: [
                    {
                        fieldName: "[Date].[Fiscal]"
                    }
                ],
                columns: [
                    {
                        fieldName: "[Customer].[Customer Geography]"
                    }
                ],
                values: [
                    {
                        measures: [
                            {
                                fieldName: "[Measures].[Internet Sales Amount]",
                            }
                        ],
                        axis: "columns"
                    }
                ],
                pagerOptions : {
                    categoricalPageSize: 3,
                    seriesPageSize: 3,
                    categoricalCurrentPage: 1,
                    seriesCurrentPage: 1
                }
            },
			targetControlID: "PivotGrid",
            enableVirtualScrolling: true
           }
        }
    });
{% endhighlight %}

{% endtabs %}

![](Paging_images/virtual-scrolling.png)

## Page Settings

The properties associated to paging are:

* EnablePaging – This property is used to enable/disable paging in PivotClient control.
* PagerOptions.CategoricalPageSize - Specifies the number of categorical columns to be displayed within a page of the PivotClient control.
* PagerOptions.SeriesPageSize - Specifies the number of series rows to be displayed within a page of the PivotClient control.
* PagerOptions.CategoricalCurrentPage - Sets the current page of the categorical axis in PivotClient control.
* PagerOptions.SeriesCurrentPage - Sets the current page of the series axis in PivotClient control.

For client mode, page setting for categorical and series axes are mandatorily needed to be set in data source property by using the following properties.

{% tabs %}

{% highlight html %}
	<div class="e-control">
	{% raw %}
	<!--Create a tag which acts as a container for PivotGrid-->
	{{ej-pivotgrid id="PivotGrid" e-dataSource=model.dataSource e-enablePaging=model.enablePaging }}
	<!--Create a tag which acts as a container for Pager. -->
	{{ej-pivotpager id="PivotPager1" e-targetControlID=model.targetControlID }}
	{% endraw %}
	</div>
{% endhighlight %}

{% highlight js %}
    export default Ember.Route.extend({
        model() {
            return {
                dataSource: {
                data: "http://bi.syncfusion.com/olap/msmdpump.dll", //data
                catalog: "Adventure Works DW 2008 SE",
                cube: "Adventure Works",
                rows: [
                    {
                        fieldName: "[Date].[Fiscal]"
                    }
                ],
                columns: [
                    {
                        fieldName: "[Customer].[Customer Geography]"
                    }
                ],
                values: [
                    {
                        measures: [
                            {
                                fieldName: "[Measures].[Internet Sales Amount]",
                            }
                        ],
                        axis: "columns"
                    }
                ],
                pagerOptions : {
                    categoricalPageSize: 3,
                    seriesPageSize: 3,
                    categoricalCurrentPage: 1,
                    seriesCurrentPage: 1
                }
            },
			targetControlID: "PivotGrid",
            enablePaging: true
           }
        }
    });
{% endhighlight %}

{% endtabs %}
