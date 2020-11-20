
![Banner](https://github.com/Pizzo15/LPLiquidSwiftTabBar/blob/main/images/banner.jpg)

# LPLiquidSwiftTabBar

`LPLiquidSwiftTabBar` is an easy to use, animated, elegant, tab bar for iOS.
You can add up to 5 tabs with associated `UIViewController` and customize some styling parameters.

![LPLiquidSwiftTabBar](https://github.com/Pizzo15/LPLiquidSwiftTabBar/blob/main/images/banner_video_new.gif)

## Installation 

### CocoaPods

`LPLiquidSwiftTabBar` is available for installation trough [CocoaPods](https://cocoapods.org). For usage and installation instruction, visit their website.
To install this library simply add this line to you `Podfile`:
```
pod 'LPLiquidSwiftTabBar'
```

### Manual

1. Open up Terminal application and `cd` into your iOS project directory

2. **ONLY IF** your project is not already initialized as a git repository, run
```
$ git init
```

3. Add `LPLiquidSwiftTabBar` as a submodule by running
```
$ git submodule add https://github.com/Pizzo15/LPLiquidSwiftTabBar.git
```

4. Open the project folder and drag the `LPLiquidSwiftTabBar.xcodeproj` file into the Project Navigator of your application.
You should drag it at the same level of your blue project icon.
Then click Save on the Xcode dialog that shows up.

5. In the Project Navigator, select your application project and go to "Targets" -> "General"

6. Click the `+` button under the "Frameworks, Libraries, and Embedded Content" section and `Add` the `LPLiquidSwiftTabBar.framework`

## How to use 

### Setup

Via `storyboard`, add a `UIView` element and set its class and model to `LPLiquidSwiftTabBar`.
Then link the `LPLiquidSwiftTabBar` element to a `IBOutlet` variable in your `UIViewController`.
```
@IBOutlet weak var liquidTabBar: LPLiquidSwiftTabBar!
```

You can start adding tab items to the tab bar by using the `add(newLiquidTabBarItem: LPLiquidSwiftTabBarItem, withViewController: UIViewController)` method.
The method takes two arguments:

1. A new `LPLiquidSwiftTabBarItem`, with a title of type `String`, which is shown when the tab is selected, and a `UIImage`, which is shown when the tab is not selected. 
You can create your `LPLiquidSwiftTabBarItem` using:
```
let tabItem = LPLiquidSwiftTabBarItem(title: "Example", image:  UIImage(systemName: "bell")!)
```

2. The `UIViewController` you want to show when the tab item is selected. You can create your `UIViewController` programmatically with 
```
let vc = UIViewController()
```
or you can pass a reference of an existing `UIViewController` using 
```
let vcIdentifier = "<your-vc-identifier>"
let vc = UIStoryboard(name: "Main", bundle: nil).instantiateViewController(withIdentifier: vcIdentifier) as! <your-vc>
```

Finally, add the new element to the tab bar:
```
liquidTabBar.add(newLiquidTabBarItem: tabItem, withViewController: vc)
```

**Important:** `LPLiquidSwiftTabBarItem` allows to use up to 5 tab items.

### Attributes

```
liquidTabBar.selectedTabItem: Int = 0

liquidTabBar.tabBarHeight: CGFloat = 72

liquidTabBar.tabBarItemTintColor: UIColor = .black

liquidTabBar.tabBarSelectedItemTintColor: UIColor = .black

liquidTabBar.tabBarItemFont: UIFont = UIFont.systemFont(ofSize: 16.0)

liquidTabBar.animationDuration: Double = 0.25
```

## License

`LPLiquidSwiftTabBar` is available under the MIT license. See the LICENSE file for more info.
