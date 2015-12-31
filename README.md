# alClick
An extenstion to Angular's ngClick directive. Code based on ngTouch's ng-click [source](https://github.com/angular/angular.js/blob/master/src/ngTouch/directive/ngClick.js#L7).

## Features
1. long press longer than 750ms will not fire a tap or click event. This means that click handler will not fire upon releasing form a drag, swipe or long press, instead it will be canceled.

PS. You can change the 750ms to your desired value from the source code.

## Install

+ Include the required source file (this path or similar)

>
``` html
<script src="dist/al-click.js"></script>
```

+ Inject the `al-click` module into your app.

>
``` JavaScript
angular.module('app', ['al-click']);
```

## Usage
+ use exactly as you would use ng-click. Example
>
``` html
<div al-click="clickHandler">Click Me</div>
```
+ In Controller

>
``` JavaScript
scope.clickHandler = function(){
  alert('heeey');
};
```
## Warning
+ this directive removes/disables angular's ng-click. You will not be able to use al-click along with ng-click. This is because both directives register listener events to the root element, so in order to have only one listener, we removed/disabled ng-click.
+ To keep ng-click enable, modify the source code and remove hte following block:

``` JavaScript
alClick.config(['$provide', function($provide) {
    $provide.decorator('ngClickDirective', ['$delegate', function($delegate) {
      $delegate[0].compile = function(){return angular.noop};
      return $delegate;
    }]);
}]);
``` 


##Other Directives
check out these other useful directives I made:

1. [alPress](https://github.com/maaljam/alPress): Angular directive for long press/touch
