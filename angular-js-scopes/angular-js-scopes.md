[Article: Understanding Scopes](https://github.com/angular/angular.js/wiki/Understanding-Scopes)

Just like JavaScript objects' prototypical inheritance, some AngularJS denotations create new scopes and inherit prototypically too: `ng-repeat`, `ng-include`, `ng-switch`, `ng-view`, `ng-controller`, .etc.

Directive `scope: {...}` creates a new scope but does not inherit prototypically--it creates an isolate scope.

		
		
