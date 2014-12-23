Ionic-Angular-Advice
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
