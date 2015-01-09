Ionic Advice
====================

## How to write an input for login with no spellcheck or autocorrect for Hybrid app

With native browser, you can use an 

```html
<input type="text" autocorrect="off" spellcheck="false">
```

for disabled autocorrect of Android and IOS.

But for Cordova/PhoneGap + Angular or Ionic application, this doesn't work.

Instead, you can use an input type="email" with ng-model-options="{allowInvalid:true}" + a form with novalidate
```html
<form novalidate>
  <input type="email" ng-model-options="{allowInvalid:true}">
</form>  
```

Now you could use it for login with email and phone in the same input 

## SVG on Android device

Don't use SVG for Android device with version under 4.4. Use PNG instead.

## input & scroll on ios

If you have multiple input with different type ( like email and number ), attention with the scroll feature. If the scroll is at false, sometimes the ios keyboard change for no reason : you click on email input and the email keyboard appears and flip to number keyboard.

## Show image store in your application on IOS

With cordova, use toInternalURL for retrieve the path of your image.
You will have a cdvfile://localhost/path/image URL.
But Angular will block this type of URL, you will have to config you app because angular is putting unsafe: prefix before link..

```
var app = angular.module( 'myApp', [] ).config( ['$compileProvider',function( $compileProvider ){ 
  $compileProvider.imgSrcSanitizationWhitelist(/^\s*(https?|file|blob|cdvfile):|data:image\//);
}
]);
```
