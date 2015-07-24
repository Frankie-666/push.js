# Push [![Build Status](https://travis-ci.org/Nickersoft/push.js.svg?branch=master)](https://travis-ci.org/Nickersoft/push.js)

### What is Push? ###

Push is the fastest way to get up and running with Javascript desktop notifications. A fairly new addition to the official specification, the Notification API allows modern browsers such as Chrome, Safari, and IE 9+ to push notifications to a user's desktop. Push acts as a cross-browser solution to this API, falling back to use  older implementations if the user's browser does not support the new API.

So just how easy is it to create a notification using Push? We can do it in just one line, actually:

```javascript
Push.create('Hello World!')
```

No constructors, just a universal API you can access from anywhere. Push is even compatible with AMD as well:

```javascript
define(['pushjs'], function (Push) {
   Push.create('Hello World!');
});
```

### Options ###

The only required argument in a Push call is a title. However, that doesn't mean you can't add a little something extra. You can pass in options to Push as well, like so:

```javascript
Push.create('Hello World!', {
    body: 'This is some body content!',
    icon: {
        x16: 'images/icon-x16.png',
        x32: 'images/icon-x32.png'
    },
    timeout: 5000
});
```

#### Available Options ####

* __body__: The body text of the notification.
* __icon__: Can be either the URL to an icon image or an array containing 16x16 and 32x32 pixel icon images (see above).
* __onClick__: Callback to execute when the notification is clicked.
* __onClose__: Callback to execute when the notification is closed (obsolete).
* __onError__: Callback to execute when if the notification throws an error.
* __onShow__: Callback to execute when the notification is shown (obsolete).
* __tag__: Unique tag used to identify the notification. Can be used to later close the notification manually.
* __timeout__: Time in milliseconds until notification closes automatically.
