---
description: Here is a list of TVJS methods that are provided by the tvOS library.
seo-description: Here is a list of TVJS methods that are provided by the tvOS library.
seo-title: TVJS Methods
solution: Marketing Cloud,Analytics
title: TVJS Methods
topic: Developer and implementation
uuid: a7bfa85a-0d6e-4f51-9a9e-70429c2a9806
index: y
internal: n
snippet: y
---

# TVJS Methods{#tvjs-methods}

Here is a list of TVJS methods that are provided by the tvOS library.

## Configuration Methods {#section_5F82FD2F6A0546B3B4E80DF832E11634}

### version

Returns the current version of the Adobe Mobile library.

**Syntax**: `version()`
  
**Returns**: `String`
  
**Parameters**: None
  
**Example**: `var sdkVersion = ADBMobile.version();`

### privacyStatus

Returns the NSUInteger representation of the privacy status enum for current user.

Here are the options:

* `ADBMobilePrivacyStatusOptIn` (1) : Hits are sent immediately.
* `ADBMobilePrivacyStatusOptOut` (2) : Hits are discarded.
* `ADBMobilePrivacyStatusUnknown` (3) : If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded).
  
  If offline tracking is not enabled, hits are discarded until the privacy status changes to opt-in.
  
* Default: The default value is set in `ADBMobileConfig.json`.
* **Syntax**: `privacyStatus()`
* **Returns**: Number
* **Parameters**: None
* **Example**: `var privacyStatus = ADBMobile.privacyStatus();`

### setPrivacyStatus

Sets the privacy status for the current user to one of the following values:

* `ADBMobilePrivacyStatusOptIn` : Hits are sent immediately.
* `ADBMobilePrivacyStatusOptOut` : Hits are discarded.
* `ADBMobilePrivacyStatusUnknown` : If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded).
  
If offline tracking is not enabled, hits are discarded until the privacy status changes to opt-in.
  
* **Syntax**: `setPrivacyStatus(privacyStatus)`
* **Returns**: N/A
* **Parameters**:

  `privacyStatus`	

  * Type: ADBMobilePrivacyStatus
  * New privacy status for this user.

* **Example**: 

  `ADBMobile.setPrivacyStatus(ADBMobilePrivacyStatusOptIn);`

### lifetimeValue

Returns the lifetime value of the current user.

* Default: 0
* **Syntax**: `lifetimeValue()`
* **Returns**: `Number`
* **Parameters**: None
* **Example**: `var ltv = ADBMobile.lifetimeValue();`

### userIdentifier

Returns the user identifier if a custom identifier has been set. Returns nil if a custom identifier is not set.

Default: nil

Important: If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous custom or automatically generated visitor ID is retrieved and stored as the custom user identifier. This preserves visitor data between SDK upgrades. For new installations on the 4.x SDK, user identifier is nil until set.

* **Syntax:** userIdentifier()
* **Returns**: String
* **Parameters**: None
* **Example**: `var uid = ADBMobile.userIdentifier();`

### setUserIdentifier

Sets the user identifier.

* **Syntax**: `setUserIdentifier(userId)`
* **Returns**: N/A
* **Parameters**:

  `userID`

  * Type: String
  * New identifier for this user.

* **Example**:
  
  `ADBMobile.setUserIdentifier(‘myUserId’);`

### setAdvertisingIdentifier

Sets the IDFA in the SDK, and the IDFA will be sent in lifecycle if it has been set in the SDK. The IDFA can also be accessed in Signals (Postbacks).

>[!IMPORTANT]
>
>Retrieve the IDFA from Apple APIs only if you are using an ad service. If you retrieve IDFA, and are not using it properly, your app might be rejected.

* **Syntax**: `setAdvertisingIdentifier(idfa)`
* **Returns**: N/A
* **Parameters**:
  
  `idfa`

  * Type: String
  * IDFA retrieved from Apple API.

* **Example**: `ADBMobile.setAdvertisingIdentifier(‘myIdfa’);`

### setDebugLogging

Sets the debug logging preference.

* **Syntax**: `setDebugLogging(logging)`
* **Returns**: N/A
* **Parameters**:

  `logging`	

  * Type: Bool
  * Value indicating whether the Adobe SDK should log to the debug console.

* **Example**: `ADBMobile.setDebugLogging(true);`

## Analytics Methods {#section_F3DB9BE225F84F86BE5F8D15164C0379}

### trackStateData

Tracks an app state with optional context data. States are the views that are available in your app, such as home dashboard , app settings , cart, and so on. These states are similar to pages on a website, and trackState calls increment page views.

If the state is empty, it displays as app name app version (build) in reports. If you see this value in reports, ensure you set the state in each trackState call.

>[!TIP]
>
>This is the only tracking call that increments page views.

* **Syntax**: `trackStateData(stateName \[, contextData\])`
* **Returns**: N/A
* **Parameters**:

  `stateName`	

  * Type: String
  * Page state name.

  `contextData`

  * Type: Object
  * Additional context data for this hit.

* **Example**: `ADBMobile.trackStateData(‘homepage’, {‘userid’:12345});`

### trackActionData

Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as logons , banner taps , feed subscriptions , and other metrics.

* **Syntax**: trackActionData(actionName \[, contextData\])
* **Returns**: N/A
* **Parameters**:

  `actionName`	

  * Type: String
  * Name of the action being tracked.

  `contextData`

  * Type: Object
  * Additional context data for this hit.

* **Example**: `ADBMobile.trackActionData(‘likeClicked’, {‘imageName’:’funnyKitty’});`

### trackLocationWithLatLonData

Sends the current latitude and longitude coordinates.

Also uses points of interest (POI) that are defined in the ADBMobileConfig.json file to determine whether the location that you entered as a parameter is within any of your POI. If the current coordinates are within a defined POI, a context data variable is populated and sent with the `trackLocation` call.

* **Syntax**: `trackLocationWithLatLonData(lat, lon [, contextData]);`
* **Returns**: N/A
* **Parameters**:

 `lat`	

  * Type: Number
  * Latitude of the location.

 `lon`	

  * Type: Number
  * Longitude of the location.

 `contextData`	

  * Type: Object
  * Additional context data for this hit.

* **Example**: `ADBMobile.trackLocationWithLatLonData(43.36, -116.12, null);`

### trackLifetimeValueIncreaseJsData

Adds an amount to the user's lifetime value.

* **Syntax**: `trackLifetimeValueIncreaseJsData(increaseAmount)`
* **Returns**: N/A
* **Parameters**:

  `increaseAmount`

  * Type: Number
  * Amount to add to the user's current lifetime value.

* **Example**: `ADBMobile.trackLifetimeValueIncreaseJsData(5);`

### trackTimedActionStartData

Start a timed action with name action.

If you call this method for an action that has already started, the previous timed action is overwritten.

>[!TIP]
>
>This call does not send a hit.

* **Syntax**: `trackTimedActionStartData(name \[, contextData\])`
* **Returns**: N/A
* **Parameters**:
  
  `name`	

  * Type: String
  * Name of the timed action being started.

  `contextData`

  * Type: Object
  * Additional context data for this hit.

* **Example**: `ADBMobile.trackTimedActionStartData(‘level1’, {‘userId’:42423});`

### trackTimedActionUpdateData

Pass in data to update the context data that is associated with the given action.

The data passed in is appended to the existing data for the given action, and if the same key is already defined for action, the data is overwritten.

>[!TIP]
>
>This call does not send a hit.

* **Syntax**: `trackTimedActionUpdateData(name \[, contextData\])`
* **Returns**: N/A
* **Parameters**:

  `name`

  * Type: String
  * Name of the timed action being updated.

  `contextData`	

  * Type: Object
  * Additional context data for this hit.

* **Example**: `ADBMobile.trackTimedActionUpdateData(‘level1’);`

### trackTimedActionEndJsLogic

End a timed action.

If you provide a callback function, you can access the final time values. If no callback is provided, or if the callback returns true, the Adobe SDK automatically sends a hit. When a false is returned from the callback, the timed action hit will be suppressed.

* **Syntax**: `trackTimedActionEndJsLogic(name \[, callback\])`
* **Returns**: N/A  
* **Parameters**:
  
  `name`

  * Type: String
  * Name of the timed action being ended

  `callback`

  * Type: function(inAppDuration, totalDuration, data)
  * Callback method that will have inAppDuration (number), totalDuration (number), and data (context data object) in its parameters.
  * Note that you can suppress the final hit from being sent by the SDK by returning false in your callback function.

* **Example**: 

```
ADBMobile.trackTimedActionEndJsLogic(‘level1’, 
function(inAppDuration, totalDuration, data) {
    // do something with final values 
    return true;  
  });
```

### trackingTimedActionExistsJs

Returns whether a timed action is in progress.

* **Syntax**: trackingTimedActionExistsJs(name)
* **Returns**: Bool
* **Parameters**:
  
  `name`	

  * Type: String
  * Name of the timed action to check existence of.

* **Example**: `var actionExists = ADBMobile.trackTimedActionExistsJs(‘level1’);`

### trackingIdentifier

Returns the automatically generated visitor identifier.

This is an app-specific unique visitor ID that is generated by Adobe’s servers. If Adobe's servers cannot be reached at the time of generation, the ID is generated by using Apple's CFUUID. The value is generated at the initial launch and is stored and used from that point. This ID is preserved between app upgrades, is saved and restored during the standard application back up process, and is removed when the app is uninstalled.

>[!TIP]
>
>If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous custom or automatically generated visitor ID is retrieved and stored as the custom user identifier. This preserves visitor data between SDK upgrades. For new installations on the 4.x SDK, the user identifier is `nil`, and the tracking identifier is used. For more information, see the userIdentifier row below.

* **Syntax**: `trackingIdentifier()`
* **Returns**: String
* **Parameters**: None
* **Example**: `var trackingId = ADBMobile.trackingIdentifier();`

### trackingSendQueuedHits

Forces the library to send all hits in the offline queue no matter how many are currently queued.

* **Syntax**: `trackingSendQueuedHits()`
* **Returns**: N/A
* **Parameters**: None
* **Example**: `ADBMobile.trackingSendQueuedHits();`

### trackingClearQueue

Clears all hits from the offline queue.

* **Syntax**: trackingClearQueue()
* **Returns**: N/A
* **Parameters**: None
* **Example**: ADBMobile.trackingClearQueue();

### trackingGetQueueSize

Retrieves the number of hits currently in the offline queue.

* **Syntax**: `trackingGetQueueSize()`
* **Returns**: Number
* **Parameters**: None
* **Example**: `var queueSize = ADBMobile.trackingGetQueueSize();`

## Audience Manager Methods {#section_0155C4DF04644EDAAF6159C420A158DE}

### audienceVisitorProfile

Returns the visitor profile that was most recently obtained.

Returns null if no signal has been submitted yet. The visitor profile is saved in NSUserDefaults for easy access across multiple launches of your app.

* **Syntax**: audienceVisitorProfile()
* **Returns**: Object
* **Parameters**: None
* **Example**:

  `var profile = ADBMobile.audienceVisitorProfile();`

### audienceDpid

Returns the current DPID.

* **Syntax**: `audienceDpid()`
* **Returns**: String
* **Parameters**: None
* **Example**:

  `var dpid = ADBMobile.audienceDpid();`

### audienceDpuuid

Returns the current DPUUID.

* **Syntax:** `audienceDpuuid()`
* **Returns**: String
* **Parameters**: None
* **Example**:
  
  `var dpuuid = ADBMobile.audienceDpuuid();`

### audienceSetDpidDpuuid

Sets the dpid and dpuuid , and if they are set, they are sent with each signal.

* **Syntax**: `audienceSetDpidDpuuid(dpid, dpuuid)`
* **Returns**: N/A
* **Parameters**:
  
  `dpid`

  * Type: String
  * Audience Manager data provider ID.

  `dpuuid`
  
  * Type: String
  * Identifier for the user and data provider combination.

* **Example**: `ADBMobile.audienceSetDpidDpuuid(‘myDpid’, ‘userDpuuid’);`

### audienceSignalWithDataJsCallback

Sends Audience Manager a signal with traits and gets the matching segments that are returned in a callback function.

* **Syntax**:
  
  `audienceSignalWithDataJsCallback(traits \[, callback\])`

* **Parameters**:
  
  `traits`
  
  * Type: Object
  * Traits dictionary for this user.

  `callback`
  
  * Type: function(profile)
  * The profile returned from Audience Manager in the parameter for the callback function.

* **Example**: 

```
ADBMobile.audienceSignalWithDataJsCallback({‘trait’:’something’}, 
function(profile) {
         // do something with the user’s segments found in profile
    });
```

### audienceReset

Resets the Audience Manager UUID and purges the current visitor profile.

* **Syntax:**: `audienceReset()`
* **Returns**: N/A
* **Parameters**: None
* **Example**: `ADBMobile.audienceReset();`

## ID Service Methods {#section_BEB6DA612EA4423FB354B65ECC941335}

### visitorMarketingCloudID

Retrieves the Experience Cloud ID from the ID service.

* **Syntax:** `visitorMarketingCloudID()`
* **Returns**: String
* **Parameters**: None
* **Example**: `var mcid = ADBMobile.visitorMarketingCloudID();`

### visitorSyncIdentifiers

In addition to the Experience Cloud ID, you can set additional customer IDs to be associated with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to setCustomerIDs in the JavaScript library.

* **Syntax**: visitorSyncIdentifiers(identifiers)
* **Returns**: N/A
* **Parameters:**
  
  `identifiers`

  * Type: Object
  * Identifiers to sync to the ID service for this user.

* **Example**: ADBMobile.visitorSyncIdentifiers({‘idType’:’idValue’});

### visitorSyncIdentifiersAuthenticationState

Synchronizes the provided identifiers to the ID service.

* **Syntax**:
  
  `visitorSyncIdentifiersAuthenticationState(identifiers, authState)`

* **Returns**: N/A
* **Parameters**:

  `identifiers`

  Type: Object

  Identifiers to sync to the ID service for this user.

  `authState`	

  Type: ADBMobileVisitorAuthenticationState

  Authentication state of the user. Possible values include:

  * ADBMobileVisitorAuthenticationStateUnknown
  * ADBMobileVisitorAuthenticationStateAuthenticated
  * ADBMobileVisitorAuthenticationStateLoggedOut

* **Example**:

  `ADBMobile.visitorSyncIdentifiersAuthenticationState({'myIdType':'valueForUser'}, ADBMobileVisitorAuthenticationStateLoggedOut)`

### visitorSyncIdentifierWithTypeIdentifierAuthenticationState

Synchronizes the provided identifier type and value to the ID service.

* **Syntax**: visitorSyncIdentifierWithTypeIdentifierAuthenticationState(idType, identifier, authState)
* **Returns**: N/A
* **Parameters**:
  
  `idType`	

  Type: String
  Type of identifier you are syncing.

  `identifier`	

  Type: String
  Value of the identifier you are syncing.

  `authState`	
  
  Type: ADBMobileVisitorAuthenticationState
  Authentication state of the user. Possible values include:

  * ADBMobileVisitorAuthenticationStateUnknown
  * ADBMobileVisitorAuthenticationStateAuthenticated
  * ADBMobileVisitorAuthenticationStateLoggedOut

* **Example:** 

```
ADBMobile.visitorSyncIdentifierWithTypeIdentifierAuthenticationState('myIdType', 'valueForUser', 
ADBMobileVisitorAuthenticationStateAuthenticated);
```

### visitorGetIDsJs

Retrieves an array of read-only ADBVisitorID objects. The following code sample is an example of a VisitorID object:

```
{
    idType: "abc",
    authenticationState: 1, 
    identifier: "123"
}
```

**Syntax**: `visitorGetIDsJs()`

**Returns**: `Array\[Object\]`

**Parameters**: None

**Example**: `var myVisitorIds = ADBMobile.visitorGetIDsJs();`

## Target Methods {#section_F9F7EC2B9B7C41AFBCA2458F9F138634}

### targetThirdPartyID

Returns the third-party ID.

* **Syntax**: `targetThirdPartyID()`
* **Returns**: String
* **Parameters**: None
* **Example**:
  
  `var thirdPartyID = ADBMobile.targetThirdPartyID();`

### targetSetThirdPartyID

Sets the third-party ID.

* **Syntax**: `targetSetThirdPartyID(thirdPartyID)`
* **Returns**: N/A
* **Parameters**:

  `thirdPartyID`

  * Type: String
  * Third-party ID to use for target requests.

* **Example**: `ADBMobile.targetSetThirdPartyID(‘thirdPartyID’);`

### targetPcID

Returns the PcID.

* **Syntax**: `targetPcID()`
* **Returns**: String
* **Parameters**: None
* **Example**:

  `var pcID = ADBMobile.targetPcID();`

### targetSessionID

Returns the session ID.

* **Syntax**: `targetSessionID()`
* **Returns**: String
* **Parameters**: None
* **Example**: `var sessionID = ADBMobile.targetSessionID();`
