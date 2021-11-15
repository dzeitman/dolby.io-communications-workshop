# ClientVideoView

The Dolby Interactivity SDK will need to be extended to leverage SwiftUI/

We'll need to create a SwiftUI Struct that conforms to [UIViewRepresentable](https://www.hackingwithswift.com/quick-start/swiftui/how-to-wrap-a-custom-uiview-for-swiftui).&#x20;

We'll also set up some properties to directly access the Dolby Interactivity SDK's VTVideoView, which is behind the code, a UIView component.

### Create the basic template:

Create a new Struct that conforms to UIViewRepresentable, allowing xcode to insert the required methods, makeUIView and updateUIView.

We will add an attach and update method&#x20;

{% tabs %}
{% tab title="Swift" %}
{% code title="ClientVideoView.swift" %}
```swift
import SwiftUI
import VoxeetSDK

struct ClientVideoView: UIViewRepresentable {
    
    var videoView:VTVideoView
    var id:UUID = UUID()
    
    init(frame:CGRect =  
    CGRect(x: 0,y: 0, width: 350, height:200)){
        self.videoView  = VTVideoView(frame: frame)
    }
    
    
    func makeUIView(context: Context) -> VTVideoView {
        return  self.videoView
    }
    
    func updateUIView(_ uiView: VTVideoView, context: Context) {}
    
    
    func attach( participant: VTParticipant, stream: MediaStream){
        self.videoView.attach(participant: participant, 
        stream: stream)
    }
    
    func update(_ stream:MediaStream){
        self.videoView.mediaStream = stream
    }
    
    func unattach(){
        self.videoView.unattach()
    }

}

```
{% endcode %}
{% endtab %}
{% endtabs %}
