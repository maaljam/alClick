# alClick
An extenstion to Angular's ngClick directive. Code based on ngTouch's ng-click [source](https://github.com/angular/angular.js/blob/master/src/ngTouch/directive/ngClick.js#L7).

## Features
1. long press longer than 750ms will not fire a tap or click event. This means that click handler will not fire upon releasing form a drag, swipe or long press, instead it will be canceled.


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
