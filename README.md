# Jelly 1.0

![Jelly-Animators: Elegant Viewcontroller Animations in Swift](https://github.com/SebastianBoldt/Jelly/blob/master/Github/Jellyfish.png)

[![CI Status](https://travis-ci.org/SebastianBoldt/Jelly.svg?style=flat)](https://travis-ci.org/SebastianBoldt/Jelly)
[![Version](https://img.shields.io/cocoapods/v/Jelly.svg?style=flat)](http://cocoapods.org/pods/Jelly)
[![License](https://img.shields.io/cocoapods/l/Jelly.svg?style=flat)](http://cocoapods.org/pods/Jelly)
[![Platform](https://img.shields.io/cocoapods/p/Jelly.svg?style=flat)](http://cocoapods.org/pods/Jelly)
[![Twitter](https://img.shields.io/badge/twitter-@sebastianboldt-blue.svg?style=flat)](http://twitter.com/sebastianboldt)

Jelly provides custom view controller animations with just a few lines of code. 
No need to create your own PresentationController or Animator-Objects.
A Jelly-Animator will do the heavy lifting for you.

## How to use 

Jelly is super easy to use. 

1. Create a *JellyPresentation* Object
2. Initialize a *JellyAnimator* using the *JellyPresentation* Object created in Step 1.
3. Call the *prepare(viewController:UIViewController)* Function
4. Finally call the native *UIViewController* presentation function.

```swift
override func viewDidLoad() {
    super.viewDidLoad()
    let presentation = JellySlideInPresentation()
    self.jellyAnimator = JellyAnimator(presentation:presentation)
    self.jellyAnimator?.prepare(viewController: viewController)
    self.present(viewController, animated: true, completion: nil)
}

```

***DO NOT FORGET TO KEEP A STRONG REFERENCE***

```swift 
class CustomVC : UIViewController {
    var jellyAnimator: JellyAnimator?
    override func viewDidLoad() {
        super.viewDidLoad()
        // Setup your Animator here 
        // ....
        // And assign it
        self.jellyAnimator = createdAnimator.
    }
}
```
Because the *transitioningDelegate* of a *UIViewController* is weak, you need to 
hold a strong reference to the *JellyAnimator* inside the *UIViewController* you are presenting from

That's it

## Example

You can use Jelly to build your own Alert-Views using ViewControllers designed by yourself.

TODO: ADD GIFS OVER HERE 

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Requirements

## Installation

Jelly is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod "Jelly"
```

## Author

Sebastian Boldt, self.dealloc@googlemail.com

## License

Jelly is available under the MIT license. See the LICENSE file for more info.
