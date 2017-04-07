# How To SetupGoogle Analytics For iOS Properly

How to setup GoogleAnalytics for iOS properly, without Firebase in CocoaPods
# 1. Init CocoaPods(in Terminal): <br>
```ruby
pod init
```

The Podfile should looks like this for now:  

```ruby

# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'

target 'YOUR_PROJECT_NAME' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!

  # Pods for YOUR_PROJECT_NAME

end

```
# 2. Add to Podfile(in Podfile): <br>
```pod 'GoogleAnalytics'```

The Podfile should looks like this for now:  

```ruby
# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'

target 'YOUR_PROJECT_NAME' do
  # Comment the next line if you're not using Swift and don't want to use dynamic frameworks
  use_frameworks!

  # Pods for YOUR_PROJECT_NAME
  pod 'GoogleAnalytics'

end

```
# 3. Install CocoaPod (in Terminal): <br>
```ruby
pod install
```

# 4. In case if it is <b>Swift</b> project (in Xcode):

Add `Bridging-Header.h` to your project.

Add the following code to Bridgin-Header <br>
```Objective-C 
#import "GAI.h"
#import "GAIDictionaryBuilder.h"
#import "GAIFields.h"
#import "GAILogger.h" 
```

# 5. In AppDelegate  (in Xcode):

Add to ```ruby didFinishLaunchingWithOptions ``` method the following code to init Google Analytics

```ruby 

GAI.sharedInstance().tracker(withTrackingId: "YOUR_TRACKING_ID")

```
## Done

That's all steps that you need to add Google Analytics to your project.

Take a look at two CocoaPods and find a difference 
```ruby
pod 'Google/Analytics'
``` :
![alt tag](https://github.com/dimaosa/HowToSetupGoogleAnalyticsForiOS/blob/master/Images/Google_Analytics.png)

And with ```ruby
pod 'GoogleAnalytics'
``` :
![alt tag](https://github.com/dimaosa/HowToSetupGoogleAnalyticsForiOS/blob/master/Images/GoogleAnalytics.png)

