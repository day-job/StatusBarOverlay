<p align="center">

</p>

StatusBarOverlay [![Language: Swift 4.0](https://img.shields.io/badge/Swift-4.0-orange.svg)](https://swift.org)
------------------------------



StatusBarOverlay will automatically show a "No Internet Connection" bar when your app loses connection, and hide it again. It supports apps which hide the status bar and The Notch

## Features

* Just a few lines of code and StatusBarOverlay will automatically show & hide when internet connection is lost & regained
* Support for apps that hide the status bar permanently
* Support for the iPhone X Notch
* Optionally you can choose to show the status bar anytime with custom text, eg for Debug or Demo modes
* Optionally you can show a drop down message, below the status bar, with a click handle, great for nonintrusive alerts
* Fully customisable colors & text

## How to install

Add this to your CocoaPods Podfile
```
pod 'StatusBarOverlay'
```

## How to use

In your ```AppDelegate.didFinishLaunchingWithOptions()``` method you can call ```StatusBarOverlay.host = "example.com"``` with your server url. StatusBarOverlay will use this to check connectivity

In your ```Info.plist``` file set ```UIViewControllerBasedStatusBarAppearance = true```

If you use a common UIViewController subclass, add the following to it. All of view controllers show override these methods, so its best to use a common UIViewController subclass
```swift
import UIKit
import StatusBarOverlay // if StatusBarOverlay is in CocoaPod

extension CommonViewController {

override var preferredStatusBarStyle: UIStatusBarStyle {
return StatusBarOverlay.preferredStatusBarStyle
}

override var prefersStatusBarHidden: Bool {
let hidden = StatusBarOverlay.prefersStatusBarHidden
print("prefersStatusBarHidden \(hidden)")
return StatusBarOverlay.prefersStatusBarHidden
}

override var preferredStatusBarUpdateAnimation: UIStatusBarAnimation {
return StatusBarOverlay.preferredStatusBarUpdateAnimation
}
}
```

Thats it. Run your app, try turning on and off airplane mode and the No Internet Connection bar will show and hide.
On the simulator sometimes the hiding event isnt fired. All devices work normally

## Dependencies

* Alamofire is required for the connectivity events

## Get these while stocks last :)

An elegant solution for keeping views visible when the keyboard is being shown
https://github.com/IdleHandsApps/IHKeyboardAvoiding

Button styles that are centralied and reusable, and hooked up to InterfaceBuilder
https://github.com/IdleHandsApps/DesignableButton

An easy way to make your NavBar transparent
https://github.com/IdleHandsApps/UINavigationBar-Transparent

## Author

* Fraser Scott-Morrison (fraserscottmorrison@me.com)

It'd be great to hear about any cool apps that are using StatusBarOverlay

## License

Distributed under the MIT License
