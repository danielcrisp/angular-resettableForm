# angular-resettableForm

> **Adds $setPristine method to ngForm for AngularJS v1.0.x**


This module was originally written by the user [Jupiter](http://stackoverflow.com/users/2335217/jupiter) on StackOverflow.

I have published it here and on Bower so I can install it in my projects.

All credit goes to Jupiter!

[Original post here](http://stackoverflow.com/questions/12603914/reset-form-to-pristine-state-angularjs-1-0-x)

## Remember

**You only need to use this if you are using AngularJS v1.0.x.**

The `$setPristine` method is [available](https://code.angularjs.org/1.1.5/docs/api/ng.directive:form.FormController) in AngularJS v1.1.x onwards.

## Installation

Use Bower to fetch the files, or download them manually:

```shell
bower install angular-resettableForm --save

```

Include the script in your HTML:

```html
<script src="bower_components/angular-resettableForm/angular-resettableForm.js"></script> 
```

And your AngularJS module:

```javascript
angular.module('myApp', ['resettableForm']);
```

## Usage

Then when you want to reset a form, you can do this in your controller.

Remember to reset the model too.

```javascript
function MyCtrl($scope) {
    $scope.reset = function() {
        $scope.form.$setPristine();
        $scope.model = '';
    };
}
```

This could be applied to a button in your UI:

```html
<div ng-app="myApp">
    <div ng-controller="MyCtrl">
        <form name="form">
            <input name="requiredField" ng-model="model.requiredField" requiredm/> (Required, but no other validators)
            <p ng-show="form.requiredField.$errror.required">Field is required</p>
            <button ng-click="reset()">Reset form</button>
        </form>
        <p>Pristine: {{form.$pristine}}</p>
    </div>
</div>
```

Thanks Jupiter!
