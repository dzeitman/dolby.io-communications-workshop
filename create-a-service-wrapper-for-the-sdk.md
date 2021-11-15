# Create a service wrapper for the SDK

Create a class wrap the Interactivity SDK.  This will call the various APIs and and publish changes to it's properties.

We'll use the @Published property wrapper to capture  and publish attendees as they join the conference.

```
class DolbyInteractiveService: ObservableObject {

    // Conference attendee dictionary
    @Published var attendees = [String:VideoStream]()
}
```

Create an extension that conforms to VTConferenceDelegate:

```
extension DolbyInteractiveService: VTConferenceDelegate {
    func statusUpdated(status: VTConferenceStatus) {
        <#code#>
    }
    
    func permissionsUpdated(permissions: [Int]) {
        <#code#>
    }
    
    func participantAdded(participant: VTParticipant) {
        <#code#>
    }
    
    func participantUpdated(participant: VTParticipant) {
        <#code#>
    }
    
    func streamAdded(participant: VTParticipant, stream: MediaStream) {
        <#code#>
    }
    
    func streamUpdated(participant: VTParticipant, stream: MediaStream) {
        <#code#>
    }
    
    func streamRemoved(participant: VTParticipant, stream: MediaStream) {
        <#code#>
    }
    
    
}


```

This extension will receive delegation calls from the SDK. You'll place most of your code and update additional properties on the DolbyInteractiveService class. &#x20;
