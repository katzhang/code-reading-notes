[Github repo](https://github.com/kenyee/angularjs-cart)

An AngularJS sample application.

###app.js:

* The app is wrapped up in a app-level module:

		var storeApp = angular.module('AngularStore', [])
			
* Create a config function via the Module API and have the $routeProvider injected into it:

		config.(['$routeProvider', function($routeProvider) {
		$routeProvider.
			when.(..., {
				templateUrl: '',
				controller: ...
			})
		}])
		
* Register a `DataService` to modules via Module API by using Module#factory

		storeApp.factory("DataService", function() {
			//Instantiate new store and shoppingCart objects
			//Return a data object with store and cart
		})
		
###controller.js
* By definition the controller should be a constructor function. It also sets up the scope. In our case the scope is on a globally application-level.

		function storeController($scope, $routeParams, DataService) {
			$scope.store = DataService.store;
			...
		}
		
* $routeParams is an object that contains URL parameters: `$routeParams.productSku`

###store.htm
* Data-binding and filter: the `<input` is bound to a variable with the same name as `search` in the data model and keep the two in sync. Whatever changes in the `<input>`, the filter input changes too.
* Pipe sign (|) is used to invoke AngularJS filters. `orderBy` and `filter` are Angular filters.
* Note that `ngRepeat` not only instantiates a template once per item from a collection, it also makes sure each template instance gets its own scope. 

		<input ng-model="search">
		...
		<tr ng-repeat="product in store.products | orderBy: 'name' | filter: search" >

* Directives can be injected as values of elements' attributes, like `<a href="#/products/{{product.sku}}">`, or as text nodes. But for `image` element's `src` attribute, use `ngSrc` to avoid bugs:

		<img ng-src="img/products/{{product.sku}}.jpg">
		
* If the exression inside `ngDisable` is truth, then special attribute `disabled` will be set on the element.

		<a href="default.htm#/cart" title="go to shopping cart" ng-disabled="cart.getTotalCount() < 1">


		
