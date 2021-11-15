# App Delegate

By default, XCode generates the SwiftUI project template without an AppDelegate.  It is up to the developer to create the file and code.

* Create an AppDelegate Swift File
* Add an AppDelegate Class;  See the example below
* &#x20; Insert the SDK's setup code inside the method:  **func application, didFinishLaunchingWithOptions**
  * Insert code to initialize SDK
  * Set the defaultVideo property to equal true

{% hint style="success" %}
Set VoxeetSDK.shared.conference.defaultVideo = **true**
{% endhint %}

{% code title="AppDelegate.swift" %}
```swift
import UIKit
import VoxeetSDK

//@UIApplicationMain
class AppDelegate: UIResponder, UIApplicationDelegate {

    func application(_ application: UIApplication, 
    didFinishLaunchingWithOptions 
    launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        
        print(VoxeetSDK.version())
        
        
        // Voxeet SDK initialization.
        VoxeetSDK.shared.initialize(consumerKey: consumerKey, 
        consumerSecret: consumerSecret)
        
        // Example of public variables to change the conference 
       // behavior.
        VoxeetSDK.shared.notification.push.type = .none
        VoxeetSDK.shared.conference.defaultBuiltInSpeaker = true
        VoxeetSDK.shared.conference.defaultVideo = true
        
//        VoxeetUXKit.shared.appearMaximized = true
//        VoxeetUXKit.shared.telecom = true
        
        return true
    }
    
  
}

```
{% endcode %}

{% hint style="success" %}
Tip: The code example above was pulled and mofified directly from the Sample iOS project example provide in the Interactivity SDK.&#x20;
{% endhint %}
