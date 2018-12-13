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
    
**Example**: `var&nbsp;sdkVersion&nbsp;=&nbsp;ADBMobile.version();`

### privacyStatus

Returns the NSUInteger representation of the privacy status enum for current user.

Here are the options:

*   `ADBMobilePrivacyStatusOptIn` (1) : Hits are sent immediately.
*   `ADBMobilePrivacyStatusOptOut` (2) : Hits are discarded.
*   `ADBMobilePrivacyStatusUnknown` (3) : If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded).
    
    If offline tracking is not enabled, hits are discarded until the privacy status changes to opt-in.
    
*   Default: The default value is set in `ADBMobileConfig.json`.
*   **Syntax**: `privacyStatus()`
*   **Returns**: Number
*   **Parameters**: None
*   **Example**: `var&nbsp;privacyStatus&nbsp;=&nbsp;ADBMobile.privacyStatus();`

### setPrivacyStatus

Sets the privacy status for the current user to one of the following values:

*   `ADBMobilePrivacyStatusOptIn` : Hits are sent immediately.
*   `ADBMobilePrivacyStatusOptOut` : Hits are discarded.
*   `ADBMobilePrivacyStatusUnknown` : If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded).
    
    If offline tracking is not enabled, hits are discarded until the privacy status changes to opt-in.
    
*   **Syntax**: `setPrivacyStatus(privacyStatus)`
*   **Returns**: N/A
*   **Parameters**:

    `privacyStatus`	

      * Type: ADBMobilePrivacyStatus
      * New privacy status for this user.

*   **Example**: 

    `ADBMobile.setPrivacyStatus(ADBMobilePrivacyStatusOptIn);`

### lifetimeValue

Returns the lifetime value of the current user.

*   Default: 0
*   **Syntax**: `lifetimeValue()`
*   **Returns**: `Number`
*   **Parameters**: None
*   **Example**: `var&nbsp;ltv&nbsp;=&nbsp;ADBMobile.lifetimeValue();`

### userIdentifier

Returns the user identifier if a custom identifier has been set. Returns nil if a custom identifier is not set.

Default: nil

Important: If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous custom or automatically generated visitor ID is retrieved and stored as the custom user identifier. This preserves visitor data between SDK upgrades. For new installations on the 4.x SDK, user identifier is nil until set.

*   **Syntax:** userIdentifier()
*   **Returns**: String
*   **Parameters**: None
*   **Example**: `var&nbsp;uid&nbsp;=&nbsp;ADBMobile.userIdentifier();`

### setUserIdentifier

Sets the user identifier.

*   **Syntax**: `setUserIdentifier(userId)`
*   **Returns**: N/A
*   **Parameters**:

    `userID`

      * Type: String
      * New identifier for this user.

*   **Example**:
    
    `ADBMobile.setUserIdentifier(‘myUserId’);`

### setAdvertisingIdentifier

Sets the IDFA in the SDK, and the IDFA will be sent in lifecycle if it has been set in the SDK. The IDFA can also be accessed in Signals (Postbacks).

>[!IMPORTANT]
>
>Retrieve the IDFA from Apple APIs only if you are using an ad service. If you retrieve IDFA, and are not using it properly, your app might be rejected.

*   **Syntax**: `setAdvertisingIdentifier(idfa)`
*   **Returns**: N/A
*   **Parameters**:
    
    `idfa`

      * Type: String
      * IDFA retrieved from Apple API.

*   **Example**: `ADBMobile.setAdvertisingIdentifier(‘myIdfa’);`

### setDebugLogging

Sets the debug logging preference.

*   **Syntax**: `setDebugLogging(logging)`
*   **Returns**: N/A
*   **Parameters**:

    `logging`	

      * Type: Bool
      * Value indicating whether the Adobe SDK should log to the debug console.

*   **Example**: `ADBMobile.setDebugLogging(true);`

## Analytics Methods {#section_F3DB9BE225F84F86BE5F8D15164C0379}

### trackStateData

Tracks an app state with optional context data. States are the views that are available in your app, such as home dashboard , app settings , cart, and so on. These states are similar to pages on a website, and trackState calls increment page views.

If the state is empty, it displays as app name app version (build) in reports. If you see this value in reports, ensure you set the state in each trackState call.

>[!TIP]
>
>This is the only tracking call that increments page views.

*   **Syntax**: `trackStateData(stateName&nbsp;\[,&nbsp;contextData\])`
*   **Returns**: N/A
*   **Parameters**:

    `stateName`	

      * Type: String
      * Page state name.

    `contextData`

      * Type: Object
      * Additional context data for this hit.

*   **Example**: `ADBMobile.trackStateData(‘homepage’,&nbsp;{‘userid’:12345});`

### trackActionData

Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as logons , banner taps , feed subscriptions , and other metrics.

*   **Syntax**: trackActionData(actionName&nbsp;\[,&nbsp;contextData\])
*   **Returns**: N/A
*   **Parameters**:

    `actionName`	

      * Type: String
      * Name of the action being tracked.

    `contextData`

      * Type: Object
      * Additional context data for this hit.

*   **Example**: `ADBMobile.trackActionData(‘likeClicked’,&nbsp;{‘imageName’:’funnyKitty’});`

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

* **Example**: `ADBMobile.trackLocationWithLatLonData(43.36,&nbsp;-116.12,&nbsp;null);`

### trackLifetimeValueIncreaseJsData

Adds an amount to the user's lifetime value.

*   **Syntax**: `trackLifetimeValueIncreaseJsData(increaseAmount)`
*   **Returns**: N/A
*   **Parameters**:

    `increaseAmount`

      * Type: Number
      * Amount to add to the user's current lifetime value.

*   **Example**: `ADBMobile.trackLifetimeValueIncreaseJsData(5);`

### trackTimedActionStartData

Start a timed action with name action.

If you call this method for an action that has already started, the previous timed action is overwritten.

>[!TIP]
>
>This call does not send a hit.

*   **Syntax**: `trackTimedActionStartData(name&nbsp;\[,&nbsp;contextData\])`
*   **Returns**: N/A
*   **Parameters**:
    
    `name`	

      * Type: String
      * Name of the timed action being started.

    `contextData`

      * Type: Object
      * Additional context data for this hit.

*   **Example**: `ADBMobile.trackTimedActionStartData(‘level1’, {‘userId’:42423});`

### trackTimedActionUpdateData

Pass in data to update the context data that is associated with the given action.

The data passed in is appended to the existing data for the given action, and if the same key is already defined for action, the data is overwritten.

>[!TIP]
>
>This call does not send a hit.

*   **Syntax**: `trackTimedActionUpdateData(name&nbsp;\[,&nbsp;contextData\])`
*   **Returns**: N/A
*   **Parameters**:

    `name`

      * Type: String
      * Name of the timed action being updated.

    `contextData`	

      * Type: Object
      * Additional context data for this hit.

*   **Example**: `ADBMobile.trackTimedActionUpdateData(‘level1’);`

### trackTimedActionEndJsLogic

End a timed action.

If you provide a callback function, you can access the final time values. If no callback is provided, or if the callback returns true, the Adobe SDK automatically sends a hit. When a false is returned from the callback, the timed action hit will be suppressed.

*   **Syntax**: `trackTimedActionEndJsLogic(name&nbsp;\[,&nbsp;callback\])`
*   **Returns**: N/A    
*   **Parameters**:
    
    `name`

      * Type: String
      * Name of the timed action being ended

    `callback`

      * Type: function(inAppDuration, totalDuration, data)
      * Callback method that will have inAppDuration (number), totalDuration (number), and data (context data object) in its parameters.
      * Note that you can suppress the final hit from being sent by the SDK by returning false in your callback function.

*   **Example**: 

```
ADBMobile.trackTimedActionEndJsLogic(‘level1’, 
function(inAppDuration, totalDuration, data) {
     // do something with final values 
     return true;  
  });
```

### trackingTimedActionExistsJs

Returns whether a timed action is in progress.

*   **Syntax**: trackingTimedActionExistsJs(name)
*   **Returns**: Bool
*   **Parameters**:
    
    `name`	

      * Type: String
      * Name of the timed action to check existence of.

*   **Example**: `var&nbsp;actionExists&nbsp;=&nbsp;ADBMobile.trackTimedActionExistsJs(‘level1’);`

### trackingIdentifier

Returns the automatically generated visitor identifier.

This is an app-specific unique visitor ID that is generated by Adobe’s servers. If Adobe's servers cannot be reached at the time of generation, the ID is generated by using Apple's CFUUID. The value is generated at the initial launch and is stored and used from that point. This ID is preserved between app upgrades, is saved and restored during the standard application back up process, and is removed when the app is uninstalled.

>[!TIP]
>
>If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous custom or automatically generated visitor ID is retrieved and stored as the custom user identifier. This preserves visitor data between SDK upgrades. For new installations on the 4.x SDK, the user identifier is `nil`, and the tracking identifier is used. For more information, see the userIdentifier row below.

*   **Syntax**: `trackingIdentifier()`
*   **Returns**: String
*   **Parameters**: None
*   **Example**: `var&nbsp;trackingId&nbsp;=&nbsp;ADBMobile.trackingIdentifier();`

### trackingSendQueuedHits

Forces the library to send all hits in the offline queue no matter how many are currently queued.

*   **Syntax**: `trackingSendQueuedHits()`
*   **Returns**: N/A
*   **Parameters**: None
*   **Example**: `ADBMobile.trackingSendQueuedHits();`

### trackingClearQueue

Clears all hits from the offline queue.

*   **Syntax**: trackingClearQueue()
*   **Returns**: N/A
*   **Parameters**: None
*   **Example**: ADBMobile.trackingClearQueue();

### trackingGetQueueSize

Retrieves the number of hits currently in the offline queue.

*   **Syntax**: `trackingGetQueueSize()`
*   **Returns**: Number
*   **Parameters**: None
*   **Example**: `var queueSize = ADBMobile.trackingGetQueueSize();`

## Audience Manager Methods {#section_0155C4DF04644EDAAF6159C420A158DE}

<table id="table_D5671FC9017B4FAE8C3D9ABB7C176385"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> audienceVisitorProfile </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained. </p> <p>Returns <span class="codeph"> null </span> if no signal has been submitted yet. The visitor profile is saved in <span class="filepath"> NSUserDefaults </span> for easy access across multiple launches of your app. </p> <p> 
     <ul id="ul_072C97BCBCF34A869274D3F81541C0C8"> 
      <li id="li_7CFDAA51F2734DD8BE2CE6823B90086F"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          audienceVisitorProfile() 
        </codeblock> </p> </li> 
      <li id="li_F46FBB37F692478D86937700B3D06897"> <p><b>Returns</b>: Object </p> </li> 
      <li id="li_6C0BB405D5414E86B7F2191B83A3999A"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_A636BB2D06464E1982D3E77828B80AA4"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         var&amp;nbsp;profile&amp;nbsp;=&amp;nbsp;ADBMobile.audienceVisitorProfile(); 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceDpid </td> 
   <td colname="col2"> <p>Returns the current DPID. </p> <p> 
     <ul id="ul_A6723C586487480FB48B181FD6568196"> 
      <li id="li_15B2DFC4E01B4DAD8BB71EE51E431377"> <p><b>Syntax</b>: </p> 
       <codeblock class="syntax c">
         audienceDpid() 
       </codeblock> </li> 
      <li id="li_64D366D1B4414D9E996F4B48BD2D526F"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_0C3FA3F818E64E3383A8F118222360BF"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_E9E35CA0FE624A4B8029567CAAD926C6"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         var&amp;nbsp;dpid&amp;nbsp;=&amp;nbsp;ADBMobile.audienceDpid(); 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceDpuuid </td> 
   <td colname="col2"> <p>Returns the current DPUUID. </p> <p> 
     <ul id="ul_2931446EADFD4900B32B517F9A87009A"> 
      <li id="li_7C6A8F6A7B804D20979520507E3F8353"> <p><b>Syntax:</b> </p> 
       <codeblock class="syntax c">
         audienceDpuuid() 
       </codeblock> </li> 
      <li id="li_78916BE104C844CDBD56B19444F30383"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_233642FE1F234467A74244011013D18E"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_06AA7EBA5B7442619A2F7D2557693BBB"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         var&nbsp;dpuuid&nbsp;=&nbsp;ADBMobile.audienceDpuuid();
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceSetDpidDpuuid </td> 
   <td colname="col2"> <p>Sets the <span class="codeph"> dpid </span> and <span class="codeph"> dpuuid </span>, and if they are set, they are sent with each signal. </p> <p> 
     <ul id="ul_2085879BA4154C84B3D145283E759E1D"> 
      <li id="li_B1DF802CB92F416CB5ACFBAFBB1E9157"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          audienceSetDpidDpuuid(dpid,&amp;nbsp;dpuuid) 
        </codeblock> </p> </li> 
      <li id="li_83B9E5E020D54304AFB88047F3C1CAB1"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_5226A3102759415A943EA8B8E437676E"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_B0A251CDEEEA470AAAB0EC3128ED0663">  
       </table> </li> 
      <li id="li_039FDC6661CB47AFAE78B2B67C4053AE"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.audienceSetDpidDpuuid(‘myDpid’,&amp;nbsp;‘userDpuuid’); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceSignalWithDataJsCallback </td> 
   <td colname="col2"> <p>Sends Audience Manager a signal with traits and gets the matching segments that are returned in a callback function. </p> <p> 
     <ul id="ul_7D32D7DBC647483CACB7FCA581F99B25"> 
      <li id="li_4679EDEB8FAC4B7DAB0AD909EA059F95"> <p><b>Syntax</b>: </p> 
       <codeblock class="syntax c">
         audienceSignalWithDataJsCallback(traits&amp;nbsp;[,&amp;nbsp;callback]) 
       </codeblock> </li> 
      <li id="li_7801DC61F5AF4A4BB3033A1CA1009928"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_D14A6B0C4D0C49668E0E6442D4042259">  
       </table> </li> 
      <li id="li_6FF5341F7787444D821A1A6475F39797"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.audienceSignalWithDataJsCallback({‘trait’:’something’},&nbsp;function(profile)&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;the&nbsp;user’s&nbsp;segments&nbsp;found&nbsp;in&nbsp;profile&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> audienceReset </td> 
   <td colname="col2"> <p>Resets the Audience Manager UUID and purges the current visitor profile. </p> <p> 
     <ul id="ul_E5E1282096B14B93B407769B7804D689"> 
      <li id="li_3FEDCBBCFA44492BAD75243E27F5EDE7"> <p><b>Syntax:</b>: 
        <codeblock class="syntax c">
          audienceReset() 
        </codeblock> </p> </li> 
      <li id="li_27663936170E4148B55A9FEA10D8CFB0"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_416FB2E8563045FE8B54A14D15479A70"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_A8A74ABFC8AD43F68C78BA49E978BA15"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.audienceReset(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## ID Service Methods {#section_BEB6DA612EA4423FB354B65ECC941335}

<table id="table_37452471A2454A1580F20E71F0BBF016"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> visitorMarketingCloudID </td> 
   <td colname="col2"> <p>Retrieves the Experience Cloud ID from the ID service. </p> <p> 
     <ul id="ul_1D3F035C09AA4979837ED85FEC3DEE99"> 
      <li id="li_4D511019CB0B4C65BFCDB34A13E92285"> <p><b>Syntax:</b> 
        <codeblock class="syntax c">
          visitorMarketingCloudID() 
        </codeblock> </p> </li> 
      <li id="li_3CCD61CD1EF54A44BA6FE6BD005DE48A"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_8E3B6EEB46AF4288BD100D2DC9689809"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_D6F5AA5CF72048C58244A443F28B8BB8"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;ADBMobile.visitorMarketingCloudID(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorSyncIdentifiers </td> 
   <td colname="col2"> <p>In addition to the Experience Cloud ID, you can set additional customer IDs to be associated with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to <span class="filepath"> setCustomerIDs </span> in the JavaScript library. </p> <p> 
     <ul id="ul_F16A7ADC1A5946FFB6DD2DB4FA508E45"> 
      <li id="li_84E1F1FC1C16459990478CA16600F348"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          visitorSyncIdentifiers(identifiers) 
        </codeblock> </p> </li> 
      <li id="li_7146D932519C453C831F3A7EC7552767"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_AD2737FA90D14459AA52B07E41C7BC39"> <p><b>Parameters:</b> </p> <p>  </p>
       <table id="table_EC2F88D543EF44A4BA2A5C434AC6D26C">  
       </table> </li> 
      <li id="li_3A600E5A64904684A0ACAA26604BED55"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.visitorSyncIdentifiers({‘idType’:’idValue’}); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorSyncIdentifiersAuthenticationState </td> 
   <td colname="col2"> <p> Synchronizes the provided identifiers to the ID service. </p> <p> 
     <ul id="ul_638172BE3D064F08B9B7F23516DA610F"> 
      <li id="li_D1DD1D706FF64830A0D8E2A1904893E8"> <p><b>Syntax</b>: </p> 
       <codeblock class="syntax c">
         visitorSyncIdentifiersAuthenticationState(identifiers,&amp;nbsp;authState) 
       </codeblock> </li> 
      <li id="li_58DF06F855DC4208A4B187561D224D86"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_4B546B12B1594E56AEA89D4D1B804AB4"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_035F8CC847934B9D9A30FA25505D5E74">  
       </table> </li> 
      <li id="li_853E658C7BDC41758793846200E270C0"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.visitorSyncIdentifiersAuthenticationState({'myIdType':'valueForUser'},&amp;nbsp;ADBMobileVisitorAuthenticationStateLoggedOut); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorSyncIdentifierWithTypeIdentifierAuthenticationState </td> 
   <td colname="col2"> <p> Synchronizes the provided identifier type and value to the ID service. </p> <p> 
     <ul id="ul_80D28A47C277486FA0E921024C056BD5"> 
      <li id="li_ADEA6CAE316E4090AF17F4438B744B04"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          visitorSyncIdentifierWithTypeIdentifierAuthenticationState(idType,&amp;nbsp;identifier,&amp;nbsp;authState) 
        </codeblock> </p> </li> 
      <li id="li_06107B27AB35499E8C8E2FCE0BDBEBED"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_7406351A83C24CA78919BB0FA4D424B0"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_DF42EAE30B604324B8E5E007BA6C8D30">  
       </table> </li> 
      <li id="li_70E17AC056D94B7ABCAF7ED8A90690F3"> <p> <b>Example:</b> 
        <codeblock class="syntax c">
          ADBMobile.visitorSyncIdentifierWithTypeIdentifierAuthenticationState('myIdType',&amp;nbsp;'valueForUser',&amp;nbsp;ADBMobileVisitorAuthenticationStateAuthenticated); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorGetIDsJs </td> 
   <td colname="col2"> <p>Retrieves an array of read-only <span class="codeph"> ADBVisitorID </span> objects. The following code sample is an example of a VisitorID object: </p> 
    <codeblock>
      {&nbsp;&nbsp;&nbsp;&nbsp;idType:&nbsp;"abc",&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;authenticationState:&nbsp;1,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;identifier:&nbsp;"123"} 
    </codeblock> <p> <b>Syntax</b>: </p> 
    <codeblock class="syntax c">
      visitorGetIDsJs() 
    </codeblock> <p><b>Returns</b>: Array[Object] </p> <p><b>Parameters</b>: None </p> <p> <b>Example</b>: </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;myVisitorIds&amp;nbsp;=&amp;nbsp;ADBMobile.visitorGetIDsJs(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Target Methods {#section_F9F7EC2B9B7C41AFBCA2458F9F138634}

<table id="table_D93105E884F249ADBABA513E6E600931"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> targetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Returns the third-party ID. </p> <p> 
     <ul id="ul_E665EC01B14E4AB78A02567ED190D076"> 
      <li id="li_33AE11DC237B4D83B68169FAAE19E0F7"> <p><b>Syntax</b>: </p> 
       <codeblock class="syntax c">
         targetThirdPartyID() 
       </codeblock> </li> 
      <li id="li_7A5839C0B7A746108C4B68D51EE98A6C"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_3245FB96A8B94ACB8901783F78F69E6C"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_CABFAACD1226409F97CED87C7337BC48"> <p> <b>Example</b>: </p> 
       <codeblock class="syntax c">
         var&amp;nbsp;thirdPartyID&amp;nbsp;=&amp;nbsp;ADBMobile.targetThirdPartyID(); 
       </codeblock> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetSetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Sets the third-party ID. </p> <p> 
     <ul id="ul_A0AB79D88B5C406F81E21AF2EDBE2E71"> 
      <li id="li_6BF95212C56F458AA82C1E02BAFEAA6E"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          targetSetThirdPartyID(thirdPartyID) 
        </codeblock> </p> </li> 
      <li id="li_47E53C489A0446958EB093766D5C9809"> <p><b>Returns</b>: N/A </p> </li> 
      <li id="li_9C1BFA58BCC64476B226C51FB669BE38"> <p><b>Parameters</b>: </p> <p>  </p>
       <table id="table_CFF69D50952D4BA393EE9D491ED072F6">  
       </table> </li> 
      <li id="li_5A06A75B040549D899ADEFE4BFB34B80"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          ADBMobile.targetSetThirdPartyID(‘thirdPartyID’); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetPcID </p> </td> 
   <td colname="col2"> <p> Returns the PcID. </p> <p> 
     <ul id="ul_59E9262E02BE47B086AAEB342A83C1EF"> 
      <li id="li_68B1646EC19D4DCA8512CDCBDB2045E6"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          targetPcID() 
        </codeblock> </p> </li> 
      <li id="li_5B7624D4CE54417B97BAC9348547245E"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_BA9424ED2161472EB5B62D3D7FD73465"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_CC2AAEAB3E1D482B8588B7E0E111ABC7"> <p> <b>Example</b>: </p> </li> 
     </ul> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;pcID&amp;nbsp;=&amp;nbsp;ADBMobile.targetPcID(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetSessionID </p> </td> 
   <td colname="col2"> <p> Returns the session ID. </p> <p> 
     <ul id="ul_ACEAA15E291C45DFAC40DDC129478102"> 
      <li id="li_A7E04E8C22A74B6FBE0645D1C5D5D289"> <p><b>Syntax</b>: 
        <codeblock class="syntax c">
          targetSessionID() 
        </codeblock> </p> </li> 
      <li id="li_DCED997628474AF194E1AEAD0C650F2B"> <p><b>Returns</b>: String </p> </li> 
      <li id="li_F15D9EC7527740389F1ADDAFDE4C428A"> <p><b>Parameters</b>: None </p> </li> 
      <li id="li_CF3D9B3F96924B4293CD96BDCCB47E9A"> <p> <b>Example</b>: 
        <codeblock class="syntax c">
          var&amp;nbsp;sessionID&amp;nbsp;=&amp;nbsp;ADBMobile.targetSessionID(); 
        </codeblock> </p> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
