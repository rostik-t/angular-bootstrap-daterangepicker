angular-bootstrap-daterangepicker
=====================

Angular directive for Dan Grossman's [bootstrap-daterangepicker](https://github.com/dangrossman/bootstrap-daterangepicker).

Demo and samples: http://kojoru.github.io/angular-bootstrap-daterangepicker

Installation
------------

Using bower:

```
bower install angular-bootstrap-daterangepicker
```

Using npm:

```
npm install angular-bootstrap-daterangepicker
```


How to use it
-------------

You should already have a bunch of scripts and CSS required for bootstrap-daterangepicker:

```
<link rel="stylesheet" type="text/css" href="bootstrap.min.css">
<link rel="stylesheet" type="text/css" href="daterangepicker-bs3.css">
<script type="text/javascript" src="jquery.min.js"></script>
<script type="text/javascript" src="bootstrap.min.js"></script>
<script type="text/javascript" src="moment.min.js"></script>
<script type="text/javascript" src="daterangepicker.js"></script>
<script type="text/javascript" src="angular.min.js"></script>
```

to the list above, you should add:

```
<script type="text/javascript" src="angular-bootstrap-daterangepicker.js"></script>
```

Then, inject `bootstrap.dateRangePicker` in your application module:

```
angular.module('myApp', ['bootstrap.dateRangePicker']);
```

and then just add `input` of type `daterange`:

```
<input type="daterange" ng-model="myDateRange">
```

or any other element with `daterange` directive (you'll have to take care of date formatting yourself then):
```
<button daterange ng-model="mySpanDateRange">{{mySpanDateRange.startDate|date}} - {{mySpanDateRange.endDate|date}}</button>
```

The result object `$scope.myDateRange` has a `startDate` and `endDate` properties, which are native javascript dates.

Implemented features so far
---------------------------

* `startDate`, `endDate`: are taken from the `ng-model` object;
* `minDate`, `maxDate`: mapped from `min-date` and `max-date` attributes;
* `dateLimit`: mapped from `limit` attribute. Number and unit are specified similarly to `moment.duration()`;
* `format`: mapped from `format` attribute;
* `separator`: mapped from `separator` attribute.
* `ranges`: mapped from `ranges` attribute. JSON string not supported for now, please use a scoped object. (see [example](http://kojoru.github.io/angular-bootstrap-daterangepicker)'s source code)
* `locale`: mapped from `locale` attribute. Can be a JSON string or scoped object. (see [example](http://kojoru.github.io/angular-bootstrap-daterangepicker)'s source code)

Example with some of the above features:
```
<input
	type="daterange"
	ng-model="dates"
	min-date="2013-09-10"
	max-date="2013-09-25"
	limit="3 days"
	format="L"
	separator="..."
	locale="{'firstDay': 1}">
```
Some other examples can be found at the project's page: http://kojoru.github.io/angular-bootstrap-daterangepicker


### Features to be implemented:

* `timePicker*`
* `show*`
* other formatting options like `*Class` and stuff 

### Build

You can run the tests by running

```
npm install
bower install
grunt
```

assuming you already have `grunt` installed, otherwise you also need to do:

```
npm install -g grunt-cli
```

Authors
-------
The directive was created by [Luis Farzati](https://github.com/luisfarzati). 
####Contributors:

* [destos](https://github.com/destos) (Patrick Forringer)
* [l310](https://github.com/l3l0) (Leszek Prabucki)
* [kojoru](https://github.com/kojoru) (Konstantin Yakushev)


