[Github repo](https://github.com/kenyee/angularjs-cart)

An AngularJS sample application.

app.js:

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