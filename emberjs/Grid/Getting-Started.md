---
title: Getting Started for Grid
description: How to create the Grid, data bind, enable paging, grouping, filtering and add summaries
platform: EmberJS
control: Grid
documentation: ug
---
# Getting started

Before we start with the Grid, please refer [Getting Started with Syncfusion EmberJS application](https://help.syncfusion.com/emberjs/overview/) for general information regarding integrating Syncfusion widget’s.

##Preparing HTML document

The grid control has the following list of external JavaScript dependencies.

* [jQuery](http://jquery.com/) 1.7.1 and later versions
* [jsRender](https://github.com/borismoore/jsrender) - to render the templates

Refer to the internal dependencies in the following table.

<table>
    <tr>
        <th>
            File
        </th>
        <th>
            Description/Usage
        </th>
    </tr>
    <tr>
        <td>
            ej.core.min.js
        </td>
        <td>
            It is referred always before using all the JS controls.
        </td>
    </tr>
    <tr>
        <td>
            ej.data.min.js
        </td>
        <td>
            Used to handle data operation and is used while binding data to the JS controls.
        </td>
    </tr>
    <tr>
        <td>
            ej.touch.min.js
        </td>
        <td>
            Used to handle touch operations in touch-enabled devices
        </td>
    </tr>
    <tr>
        <td>
            ej.print.min.js
        </td>
        <td>
            Used to handle print operation in JS controls.
        </td>
    </tr>
    <tr>
        <td>
            ej.globalize.min.js
        </td>
        <td>
            It is referred when using localization in Grid.
        </td>
    </tr>
    <tr>
        <td>
            ej.draggable.min.js
        </td>
        <td>
            Used for drag and drop an element in JS controls.
        </td>
    </tr>
    <tr>
        <td>
            ej.grid.min.js
        </td>
        <td>
            The grid's main file.
        </td>
    </tr>
    <tr>
        <td>
            ej.pager.min.js
        </td>
        <td>
            It is referred when paging is used in the Grid.
        </td>
    </tr>
    <tr>
        <td>
            ej.scroller.min.js
        </td>
        <td>
            It is referred when scrolling is used in the Grid.
        </td>
    </tr>
    <tr>
        <td>
            ej.waitingpopup.min.js
        </td>
        <td>
            It is referred when the remote data binding is used in the Grid. The waiting popup shows while requesting the server for data.
        </td>
    </tr>
    <tr>
        <td>
            ej.dropdownlist.min.js
        </td>
        <td rowspan="8">
            These files are used while enable the Editing and Filtering feature in the Grid.
        </td>
    </tr>
    <tr>
        <td>
            ej.dialog.min.js
        </td>
    </tr>
    <tr>
        <td>
            ej.button.min.js
        </td>
    </tr>
    <tr>
        <td>
            ej.autocomplete.min.js
        </td>
    </tr>
    <tr>
        <td>
            ej.datepicker.min.js
        </td>
    </tr>
    <tr>
        <td>
            ej.timepicker.min.js
        </td>
    </tr>
    <tr>
        <td>
            ej.datetimepicker.min.js
        </td>
    </tr>
    <tr>
        <td>
            ej.checkbox.min.js
        </td>
    </tr>
    <tr>
        <td>
            ej.editor.min.js
        </td>
    </tr>
    <tr>
        <td>
            ej.tooltip.js
        </td>
        <td rowspan="2">
            It is referred when toolbar is enabled in Grid.
        </td>
    </tr>
    <tr>
        <td>
            ej.toolbar.min.js
        </td>
    </tr>
    <tr>
        <td>
            ej.menu.js
        </td>
        <td>
            It is referred when excel like filter menu or context menu is enabled.
        </td>
    </tr>
    <tr>
        <td>
            ej.radiobutton.js
        </td>
        <td>
            It is referred when filtering is enabled.
        </td>
    </tr>
    <tr>
        <td>
            ej.excelfilter.js
        </td>
        <td>
            It is referred when excel like filter menu is enabled.
        </td>
    </tr>
</table>

Refer the `ej.web.all.min.js` which encapsulates all the `ej` controls and frameworks in a single file.

## Control Initialization

* Open the command prompt in the folder [ember-app](https://help.syncfusion.com/emberjs/getting-started#create-a-simple-ember-application) or the folder in which the application is created.

* Use the command [ember generate route grid/default](https://guides.emberjs.com/v2.11.0/routing/defining-your-routes/)to create template `default.hbs` file in templates folder and router `default.js` file in routes folder. It also add the routing content in `router.js`.

* Use below code in `default.hbs` in templates folder to render the grid.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data}}

{% endhighlight %}

* Use the below code in `default.js` in routes folder to bind the model to the grid.

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           data: [
                  { Name: 'Hanari Carnes', City: 'Brazil' },
                  { Name: 'Split Rail Beer & Ale', City: 'USA' },
                  { Name: 'Ricardo Adocicados', City: 'Brazil' }
              ];
           }
        }
    });

{% endhighlight %}

## Running the application

* To run the application, execute below command.

{% highlight javascript %}

 ember serve

{% endhighlight %}

* Browse to [http://localhost:4200](http://localhost:4200) to see the application. And navigate to grid sample. The component is rendered as like the below screenshot. You can make changes in the code found under app folder and the browser should auto-refresh itself while you save files.

![](Getting-started_images/Getting-started_img1.png)

## Data binding

[`Data binding`] in the grid is achieved by assigning an array of JavaScript objects to the [`dataSource`](https://help.syncfusion.com/api/js/ejgrid#members:columns-datasource) property.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols }}

{% endhighlight %}


{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           //The datasource "window.gridData" is referred from 'http://js.syncfusion.com/demos/web/scripts/jsondata.min.js'
            data: window.gridData,
            cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
          }
       }
    });

{% endhighlight %}

![](Getting-started_images/Getting-started_img2.png)
{:.image }



## Enable Paging

[Paging] can be enabled by setting the [`allowPaging`](https://help.syncfusion.com/api/js/ejgrid#members:allowpaging) to true.  This adds the pager in the bottom of the grid and page size can be customized by using the [`pageSettings.pageSize`](https://help.syncfusion.com/api/js/ejgrid#members:pagesettings-pagesize) property

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-pageSettings=model.page }}

{% endhighlight %}

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           data: window.gridData,
           page: { pageSize: 8 },
           cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}

N> Pager settings can be customized by using the [`pageSettings.pageSize`](https://help.syncfusion.com/api/js/ejgrid#members:pagesettings-pagesize) property. When it is not given the default values for `pageSize` and `pageCount` are 12 and 8 respectively.


![](Getting-started_images/Getting-started_img3.png)
{:.image }


## Enable Filtering

[`Filtering`] can be enabled by setting the `allowFiltering` to `true`. By default, the filter bar row is displayed to perform filtering, you can change the filter type by using the [`filterSetting.filterType`](https://help.syncfusion.com/api/js/ejgrid#members:filtersettings) property.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-allowFiltering=true }}

{% endhighlight %}

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
            data: window.gridData,
            cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}

![](Getting-started_images/Getting-started_img4.png)
{:.image }


## Enable Grouping

[`Grouping`] can be enabled by setting the [`allowGrouping`](https://help.syncfusion.com/api/js/ejgrid#members:allowgrouping) to `true`.  Columns can be grouped dynamically by drag and drop the grid column header to the group drop area. The initial grouping can be done by adding required column names in the [`groupSettings.groupedColumns`](https://help.syncfusion.com/api/js/ejgrid#members:groupsettings-groupedcolumns) property.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-allowGrouping=true}}

{% endhighlight %}

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
             data: window.gridData,
             cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}

![](Getting-started_images/Getting-started_img5.png)
{:.image }


Refer to the following code example for initial grouping.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-allowGrouping=true e-groupSettings=model.group}}

{% endhighlight %}

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
            data: window.gridData,
            group: { groupedColumns: ["ShipCountry", "CustomerID"] },
            cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}
![](Getting-started_images/Getting-started_img6.png)
{:.image }


## Add Summaries

[`Summaries`] can be added by setting the [`showSummary`](https://help.syncfusion.com/api/js/ejgrid#members:showsummary) to true and adding required summary rows and columns in the [`summaryRows`](https://help.syncfusion.com/api/js/ejgrid#members:summaryrows) property. For demonstration, Stock column's sum value is displayed as summary.

{% highlight html %}

{{ej-grid id="Grid" e-dataSource=model.data e-columns=model.cols e-allowPaging=true e-showSummary=true e-summaryRows=model.summaryRows e-allowGrouping=true e-groupSettings=model.group e-pageSettings=model.page}}

{% endhighlight %}

{% highlight html %}

	import Ember from 'ember';

    export default Ember.Route.extend({
      model() {
         return {
           data: window.gridData,
           page : { pageSize: 8 },
           group: { groupedColumns: ["CustomerID"] },
           summaryRows: [
                {
                  	title: "Sum",
                  	summaryColumns: [
                    { summaryType: ej.Grid.SummaryType.Sum, displayColumn: "Freight", dataMember: "Freight" }
              	  ]
              }
           ],
           cols: ["OrderID", "EmployeeID", "CustomerID", "ShipCountry", "Freight"]
           }
        }
    });

{% endhighlight %}
![](Getting-started_images/Getting-started_img7.png)
{:.image }
