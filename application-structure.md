# Application Structure

{% hint style="success" %}
SwiftUI provides many means to manage application data across views and child views.  The EnviornmentObject Property wrapper is reccommended pattern to use when building apps with many views.   This nuances of this topic discussion is deep and beyond the scope of this tutorial, we suggest you familiarize yourself with the concepts before proceeding.&#x20;

One great resource is Paul Hudson's HackingWithSwift website:

[https://www.hackingwithswift.com/quick-start/swiftui/what-is-the-environmentobject-property-wrapper](https://www.hackingwithswift.com/quick-start/swiftui/what-is-the-environmentobject-property-wrapper)
{% endhint %}

* [EnvironmentObject](https://www.hackingwithswift.com/quick-start/swiftui/what-is-the-environmentobject-property-wrapper) &#x20;
  * Model (ConferenceVideoViewModel)
  * Service  (DolbyInteractiveService)
    * Trigger updates via Notifications (Combine)
* Views
  * [Composable](https://www.hackingwithswift.com/quick-start/swiftui/how-to-create-and-compose-custom-views)&#x20;
    * Toolbar&#x20;
      * Conference name
      * Mic (Toggle)
      * Video (Toggle)
      * Participants (toggle)
        * Participants [List](https://www.hackingwithswift.com/quick-start/swiftui/building-a-menu-using-list) (Sheet)
    * Login
    * Join Conference
    * ClientVideoView (2)
      * [UIRepresentable](https://www.hackingwithswift.com/quick-start/swiftui/how-to-wrap-a-custom-uiview-for-swiftui) View for our VTVideoView

