# device-fingerprinting
A npm package to create a device fingerprint for users in front-end. You can install this package in your front-end of project to root folder. Then use below example code to get fingerprint details.


## Installation
Run the following command from the root of your project:
```
 $ bower install device-fingerprinting --save
```
or
```
 $ npm install device-fingerprinting --save
```


## Usage Overview:

#### JavaScript

```
    const DeviceFingerprinting = require("device-fingerprinting");

    var deviceFingerprint = DeviceFingerprinting().getDeviceFingerprint();
    console.log(`The device fingerprint is ${deviceFingerprint}`);

    var DeviceWithBrowserFingerprint = DeviceFingerprinting().getBrowserFingerprint();
    console.log(`The device with browser fingerprint is ${DeviceWithBrowserFingerprint}`);

    var FCMToken = DeviceFingerprinting().getFCMToken();
    console.log(`The device FCM token is ${FCMToken}`);
```


## Function details:

### 1. getDeviceFingerprint
This method will return a token according to device specification. So using this, if user try 2 different browser to login 2 different account still it give same device fingerprint, from which we can track it.

**Drawback**: This will be created according to system details. So two system with same details can have same token.   

**Accuracy**: 55%

### 2. getBrowserFingerprint
This method will return a token according to device specification + broswer details. So using this, if user is try to login in differnt incognito tabs, it give same device browser fingerprint, from which we can track it.
So this value

**Drawback**: This will be created according to system details + broswer details. So two system with same details and same broswer (and broswer version) can have same token.

**Accuracy**: 90%

### 3. getFCMToken
This method will return a Facm token that you should store in local storage of the user's browser. So using this, if user is try to login with different accounts on broswer, it give same FCM token, from which we can track it.
So this value

**Drawback**: This value will change everytime .

**Accuracy**: 95%

## Solution
Best way is to use the all 3 variables and accordingly you can track user.

### Credits

These definitions were written by [Mayuresh Sunil Khemnar](https://github.com/KhemnarMayuresh).


### LICENSE

[MIT](LICENSE)