# cordova-plugin-keyboard

> This plugin provides the `NotIonicKeyboard` object which has some functions to customize and control the keyboard. It also supports the __HideKeyboardFormAccessoryBar__ (boolean) and __KeyboardShrinksView__ (boolean) preferences in config.xml.

This plugin has only been tested in Cordova 3.2 or greater, and its use in previous Cordova versions is not recommended (potential conflict with keyboard customization code present in the core in previous Cordova versions). 

If you do use this plugin in an older Cordova version (again, not recommended), you have to make sure the HideKeyboardFormAccessoryBar and KeyboardShrinksView preference values are *always* false, and only use the API functions to turn things on/off.

This plugin was based on this Apache [project](https://github.com/apache/cordova-plugins/tree/master/keyboard) and has a compatible API.

- [Installation](#installation)
- [Methods](#methods)
    - [cordova.plugins.NotIonicKeyboard.shrinkView](#cordovapluginskeyboardshrinkview)
    - [cordova.plugins.NotIonicKeyboard.hideFormAccessoryBar](#cordovapluginskeyboardhideformaccessorybar)
    - [cordova.plugins.NotIonicKeyboard.disableScrollingInShrinkView](#cordovapluginskeyboarddisablescrollinginshrinkview)
    - [cordova.plugins.NotIonicKeyboard.hide](#cordovapluginskeyboardhide)
    - [cordova.plugins.NotIonicKeyboard.show](#cordovapluginskeyboardshow)
- [Properties](#properties)
    - [cordova.plugins.NotIonicKeyboard.isVisible](#cordovapluginskeyboardisvisible)
    - [cordova.plugins.NotIonicKeyboard.automaticScrollToTopOnHiding](#cordovapluginskeyboardautomaticscrolltotoponhiding)
- [Events](#events)
    - [keyboardDidShow](#keyboarddidshow)
    - [keyboardDidHide](#keyboarddidhide)
    - [keyboardWillShow](#keyboardwillshow)
    - [keyboardWillHide](#keyboardwillhide)
    - [keyboardHeightWillChange](#keyboardheightwillchange)
- [Releases](#releases) 

# Installation

From [npm](https://www.npmjs.com/package/cordova-plugin-keyboard) (stable)

`cordova plugin add cordova-plugin-keyboard`

From github latest (may not be stable)

`cordova plugin add https://github.com/faustopala/cordova-plugin-keyboard`

# Methods

## cordova.plugins.NotIonicKeyboard.shrinkView

Shrink the WebView when the keyboard comes up.

    cordova.plugins.NotIonicKeyboard.shrinkView(value, successCallback);

#### Description

Set to true to shrink the WebView when the keyboard comes up. The WebView shrinks instead of the viewport shrinking and the page scrollable. This applies to apps that position their elements relative to the bottom of the WebView. This is the default behaviour on Android, and makes a lot of sense when building apps as opposed to webpages.


#### Supported Platforms

- iOS

#### Quick Example

    cordova.plugins.NotIonicKeyboard.shrinkView(true);
    cordova.plugins.NotIonicKeyboard.shrinkView(false);
    cordova.plugins.NotIonicKeyboard.shrinkView(null, function (currentValue) { console.log(currentValue); });

## cordova.plugins.NotIonicKeyboard.hideFormAccessoryBar

Hide the keyboard toolbar.

    cordova.plugins.NotIonicKeyboard.hideFormAccessoryBar(value, successCallback);

#### Description

Set to true to hide the additional toolbar that is on top of the keyboard. This toolbar features the Prev, Next, and Done buttons.


#### Supported Platforms

- iOS

#### Quick Example

    cordova.plugins.NotIonicKeyboard.hideFormAccessoryBar(true);
    cordova.plugins.NotIonicKeyboard.hideFormAccessoryBar(false);
    cordova.plugins.NotIonicKeyboard.hideFormAccessoryBar(null, function (currentValue) { console.log(currentValue); });

## cordova.plugins.NotIonicKeyboard.disableScrollingInShrinkView

Disable scrolling when the the WebView is shrunk.

    cordova.plugins.NotIonicKeyboard.disableScrollingInShrinkView(value, successCallback);

#### Description

Set to true to disable scrolling when the WebView is shrunk.


#### Supported Platforms

- iOS

#### Quick Example

    cordova.plugins.NotIonicKeyboard.disableScrollingInShrinkView(true);
    cordova.plugins.NotIonicKeyboard.disableScrollingInShrinkView(false);
    cordova.plugins.NotIonicKeyboard.disableScrollingInShrinkView(null, function (currentValue) { console.log(currentValue); });
 
## cordova.plugins.NotIonicKeyboard.hide

Hide the keyboard

    cordova.plugins.NotIonicKeyboard.hide();

#### Description

Call this method to hide the keyboard

#### Supported Platforms

- iOS
- Android

#### Quick Example

    cordova.plugins.NotIonicKeyboard.hide();

## cordova.plugins.NotIonicKeyboard.show

Show the keyboard

    cordova.plugins.NotIonicKeyboard.show();

#### Description

Call this method to show the keyboard.


#### Supported Platforms

- Android

#### Quick Example

    cordova.plugins.NotIonicKeyboard.show();

# Properties

## cordova.plugins.NotIonicKeyboard.isVisible

Determine if the keyboard is visible.

    if (cordova.plugins.NotIonicKeyboard.isVisible) {
        // do something
    }

#### Description

Read this property to determine if the keyboard is visible.


#### Supported Platforms

- iOS

## cordova.plugins.NotIonicKeyboard.automaticScrollToTopOnHiding

Specifies whenether content of page would be automatically scrolled to the top of the page
when keyboard is hiding.

    cordova.plugins.NotIonicKeyboard.automaticScrollToTopOnHiding = true;

#### Description

Set this to true if you need that page scroll to beginning when keyboard is hiding.
This is allows to fix issue with elements declared with position: fixed,
after keyboard is hiding.


#### Supported Platforms

- iOS

# Events

## keyboardDidShow

This event is fired when keyboard fully shown.

    window.addEventListener('keyboardDidShow', function () {
        // Describe your logic which will be run each time keyboard is shown.
    });

#### Description

Attach handler to this event to be able to receive notification when keyboard is shown.


#### Supported Platforms

- iOS

## keyboardDidHide

This event is fired when the keyboard is fully closed.

    window.addEventListener('keyboardDidHide', function () {
        // Describe your logic which will be run each time keyboard is closed.
    });

#### Description

Attach handler to this event to be able to receive notification when keyboard is closed.


#### Supported Platforms

- iOS

## keyboardWillShow

This event fires before keyboard will be shown.

    window.addEventListener('keyboardWillShow', function () {
        // Describe your logic which will be run each time when keyboard is about to be shown.
    });

#### Description

Attach handler to this event to be able to receive notification when keyboard is about to be shown on the screen.


#### Supported Platforms

- iOS

## keyboardWillHide

This event is fired when the keyboard is fully closed.

    window.addEventListener('keyboardWillHide', function () {
        // Describe your logic which will be run each time when keyboard is about to be closed.
    });

#### Description

Attach handler to this event to be able to receive notification when keyboard is about to be closed.


#### Supported Platforms

- iOS

## keyboardHeightWillChange

This event is fired when the keyboard is fully closed.

    window.addEventListener('keyboardHeightWillChange', function (event) {
        // Describe your logic which will be run each time when keyboard is about to be closed.
        console.log(event.keyboardHeight);
    });

#### Description

Attach handler to this event to be able to receive notification when keyboard is about to be closed.


#### Supported Platforms

- iOS


# Releases

- 1.0.0 
    - Initial NPM release
    - Fix issues with external keyboards
    - Support keyboard events on window
    - Fix issues with split and undocked keyboards
    - Add keyboardHeightWillChange event
    - Fix issues with StatusBarOverlaysWebview
- 1.1.0
    - Add hide/show for Android
    - Support original keyboard event mechanism
- 1.1.1
    - Make compatible with cordova-android 3 and 4 (See [#2](/../../issues/2))
    - Add hide for iOS
- 1.1.2
    - Fix issues with hiding the accessory bar (See [#3](/../../issues/3))
- 1.1.3
    - Support hiding the accessory bar when using WKWebView as the engine (See [here](https://github.com/Telerik-Verified-Plugins/WKWebView/issues/85))
- 1.1.4
    - Fix page scrolling (See [#14](/../../issues/14))
    - Prevent possible app store rejections (See [#21](/../../issues/21)) 
- 1.1.5
    - Fix window.innerHeight when using WKWebView (See [#32](/../../issues/32))
- 1.2.0
    - Return current values of shrinkView, disableScroll and hideFormAccessoryBar in a success callback
    - Fix scroller resizing bug (See [#55](/../../issues/55))
    - Fix iOS 11.1.1 WKWebView ShrinksView bug (See [#64](/../../issues/64))

