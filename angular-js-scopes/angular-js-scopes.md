[Article: Understanding Scopes](https://github.com/angular/angular.js/wiki/Understanding-Scopes)

* Just like JavaScript objects' prototypical inheritance, some AngularJS denotations create new scopes and inherit prototypically too: `ng-repeat`, `ng-include`, `ng-switch`, `ng-view`, `ng-controller`, .etc.

   Directive `scope: {...}` creates a new scope but does not inherit prototypically--it creates an isolate scope.

   Using `object.property` in `ng-model` rather than just `property` can prevent accidentally hiding/shadowing parent scope's property that shares the same name.

  > if you need 2-way data binding to a primitive in the parent scope, use $parent, or change the model to be an object and then bind to a property of that object. This will avoid child scope hiding/shadowing of parent scope properties.


  For all scopes (prototypal or not), Angular always tracks a parent-child relationship (i.e., a hierarchy), via scope properties $parent, $$childHead and $$childTail.

* `ng-repeat` works a bit differently.
>For each item/iteration, ng-repeat creates a new scope, which prototypically inherits from the parent scope, but it also assigns the item's value to a new property on the new child scope. 

  But
  > What we want is for the inputs to affect the myArrayOfPrimitives array, not a child scope primitive property. To accomplish this, we need to change the model to be an array of objects. So, if item is an object, a reference to the original object (not a copy) is assigned to the new child scope property. Changing the child scope property's value (i.e., using ng-model, hence obj.num) does change the object the parent scope references. 


		
		
