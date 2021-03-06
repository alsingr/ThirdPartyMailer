# ThirdPartyMailer

_Interact with third-party iOS mail clients, using custom URL schemes._

![Platform iOS](https://img.shields.io/badge/platform-iOS-blue.svg)
[![Build Status](https://travis-ci.org/vtourraine/ThirdPartyMailer.svg?branch=master)](https://travis-ci.org/vtourraine/ThirdPartyMailer)
[![CocoaPods compatible](https://img.shields.io/cocoapods/v/ThirdPartyMailer.svg)](https://cocoapods.org/pods/ThirdPartyMailer)
[![MIT license](http://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/vtourraine/ThirdPartyMailer/raw/master/LICENSE.md)


## Supported mail clients

Client             | URL Scheme      | App Store
------------------ | --------------- | ---------
Sparrow            | `sparrow`       | _discontinued_
Gmail              | `googlegmail`   | [link](https://itunes.apple.com/app/id422689480?mt=8)
Dispatch           | `x-dispatch`    | [link](https://itunes.apple.com/app/id642022747?mt=8)
Spark              | `readdle-spark` | [link](https://itunes.apple.com/app/id997102246?mt=8)
Airmail            | `airmail`       | [link](https://itunes.apple.com/app/id993160329?mt=8)
Microsoft Outlook  | `ms-outlook`    | [link](https://itunes.apple.com/app/id951937596?mt=8)
Yahoo Mail         | `ymail`         | [link](https://itunes.apple.com/app/id577586159?mt=8)

Unfortunately, not all mail clients offer URL schemes to be supported by `ThirdPartyMailer`. If you’re aware of another candidate, please [let us know](https://github.com/vtourraine/ThirdPartyMailer/issues).


## How to install

With [CocoaPods](https://cocoapods.org), simply add ThirdPartyMailer to your Podfile:

```
pod 'ThirdPartyMailer'
```

Or, you can manually import the files from the Source folder.


## How to use

Getting the list of available clients:

``` swift
let clients = ThirdPartyMailClient.clients()
```

Testing the client availability (i.e. is the app installed):

``` swift
let application = UIApplication.shared

if ThirdPartyMailer.application(application, isMailClientAvailable: client) {
    // ...
}
```

Opening the client (with optional message recipient, subject, and body):

``` swift
let application = UIApplication.shared

ThirdPartyMailer.application(application, openMailClient: client, recipient: nil, subject: nil, body: nil)
```


## Requirements

ThirdPartyMailer is written in Swift 3.2, requires iOS 8.0 and above, Xcode 8.0 and above.


## Credits

ThirdPartyMailer was created by [Vincent Tourraine](http://www.vtourraine.net).


## License

ThirdPartyMailer is available under the MIT license. See the LICENSE file for more info.
