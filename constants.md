# Create the app and add Constants

* Create a new app in xcode with the SwiftUI template.
* Create a Contant.swift file Add your key and secret to a new swift file:

{% code title="Constants.swift" %}
```
let consumerKey =  "YOUR_KEY HERE"
let consumerSecret =  "YOUR SECRET HERE"


```
{% endcode %}

{% hint style="info" %}
Note we'll hardcode the client key and secret here, in production you'll want to use a more secure process. &#x20;

Refer to our documentation about the process:

[https://dolby.io/developers/interactivity-apis/reference/client-sdk/initializing](https://dolby.io/developers/interactivity-apis/reference/client-sdk/initializing)

Be sure to add this file to your gitignore file to avoid sharing your key.
{% endhint %}

Next create an app delegate to initialize the SDK.
