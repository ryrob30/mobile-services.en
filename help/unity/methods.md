---
description: List of ADBMobile.cs methods for Unity applications.
keywords: Unity
seo-description: List of ADBMobile.cs methods for Unity applications.
seo-title: ADBMobile.cs Methods, Classes, and Enumerations
solution: Marketing Cloud,Developer
title: ADBMobile.cs Methods, Classes, and Enumerations
uuid: c32ffec1-b1d0-4a23-8fc7-88408dc4bee8
index: y
internal: n
snippet: y
---

# ADBMobile.cs Methods, Classes, and Enumerations{#adbmobile-cs-methods-classes-and-enumerations}

List of ADBMobile.cs methods for Unity applications.

**Features Not Supported**

1. iOS Extensions 
1. watchOS Applications 
1. tvOS applications 
1. Use of the `AdobeDataCallback`

## Configuration Methods {#section_F3BF1D7E12504B0FBE02F6CC67A3F201}

<table id="table_8DCB06D056B14564AFCDE32F2ED71B7D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> CollectLifecycleData </p> </td> 
   <td colname="col2"> <p> Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=metrics" format="https" scope="external"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;CollectLifecycleData(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.CollectLifecycleData(); 
    </codeblock> <p> <b>Sending Additional Data</b> </p> <p>For Android, you can send in additional data with context data using the overloaded method: </p> 
    <codeblock>
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;CollectLifecycleData(Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata) 
    </codeblock> <p>To send additional data with lifecycle on iOS, this needs to be done in the objective-c code natively. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> EnableLocalNotifications (iOS only) </p> </td> 
   <td colname="col2"> <p>Enable local notifications in your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;EnableLocalNotifications(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.EnableLocalNotifications(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> GetDebugLogging </p> </td> 
   <td colname="col2"> <p>Returns the current debug logging preference. Default: false </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;bool&amp;nbsp;GetDebugLogging(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;debugEnabled&amp;nbsp;=&amp;nbsp;ADBMobile.GetDebugLogging(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> GetLifetimeValue </p> </td> 
   <td colname="col2"> <p> Returns the lifetime value of the current user. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;double&amp;nbsp;GetLifetimeValue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;lifetimeValue&amp;nbsp;=&amp;nbsp;ADBMobile.GetLifetimeValue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> GetPrivacyStatus </p> </td> 
   <td colname="col2"> <p> Returns the enum representation of the privacy status for current user. </p> <p>MOBILE_PRIVACY_STATUS_OPT_IN: Hits are sent immediately. </p> <p>MOBILE_PRIVACY_STATUS_OPT_OUT: Hits are discarded. </p> <p>MOBILE_PRIVACY_STATUS_UNKNOWN: If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. </p> <p>Default: The default value is set in <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/json_config.html" format="https" scope="external"> ADBMobileConfig.json </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBPrivacyStatus&amp;nbsp;GetPrivacyStatus(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;privacyStatus&amp;nbsp;=&amp;nbsp;ADBMobile.GetPrivacyStatus(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> GetUserIdentifier </p> </td> 
   <td colname="col2"> <p> Returns the custom user identifier if a custom identifier has been set. Returns null if a custom identifier is not set. </p> <p>Default: null </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;GetUserIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;userId&amp;nbsp;=&amp;nbsp;ADBMobile.GetUserIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> GetVersion </p> </td> 
   <td colname="col2"> <p>Gets the library version of the underlying Adobe Mobile SDK. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;GetVersion(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;version&amp;nbsp;=&amp;nbsp;ADBMobile.GetVersion(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> KeepLifecycleSessionAlive (iOS only) </p> </td> 
   <td colname="col2"> <p>Indicates to the SDK that your next resume from background should not start a new session, regardless of the value of lifecycle session timeout in your config file. </p> <p> <b>Note</b>: This method is intended to be used for apps that register for notifications while in the background and should only be called from your code that runs while your app is in the background. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;KeepLifecycleSessionAlive(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.KeepLifecycleSessionAlive(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> PauseCollectingLifecycleData (Android only) </p> </td> 
   <td colname="col2"> <p> Indicates to the SDK that your app is paused, so that lifecycle metrics are calculated correctly. For example, on pause collects a timestamp to determine previous session length. This also sets a flag so that lifecycle correctly knows that the app did not crash. See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=metrics" format="https" scope="external"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;PauseCollectingLifecycleData(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.PauseCollectingLifecycleData(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SetContext (Android only) </p> </td> 
   <td colname="col2"> <p> Indicates to the SDK that it should set its application context from the UnityPlayer's current activity </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetContext(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetContext(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SetDebugLogging </p> </td> 
   <td colname="col2"> <p>Sets the debug logging preference to enabled. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetDebugLogging&amp;nbsp;(bool&amp;nbsp;enabled); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetDebugLogging(true); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SetPrivacyStatus </p> </td> 
   <td colname="col2"> <p> Sets the privacy status for the current user to status. Set to one of the following values: </p> <p>MOBILE_PRIVACY_STATUS_OPT_IN: Hits are sent immediately. </p> <p>MOBILE_PRIVACY_STATUS_OPT_OUT: Hits are discarded. </p> <p>MOBILE_PRIVACY_STATUS_UNKNOWN: If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetPrivacyStatus(ADBPrivacyStatusstatus); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetPrivacyStatus(ADBMobile.ADBPrivacyStatus.MOBILE_PRIVACY_STATUS_OPT_IN); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SetUserIdentifier </p> </td> 
   <td colname="col2"> <p>Sets the user identifier to userId. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetUserIdentifier(string&amp;nbsp;userId); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetUserIdentifier("myCustomUserId"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SetPushIdentifier </p> </td> 
   <td colname="col2"> <p> Sets the device token for push notifications. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetPushIdentifier&amp;nbsp;(string&amp;nbsp;deviceToken) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetPushIdentifier&amp;nbsp;(deviceToken); 
    </codeblock> <p> <p>Note:  For iOS, you can obtain a push token by <a href="https://docs.unity3d.com/ScriptReference/iOS.NotificationServices.RegisterForNotifications.html" format="html" scope="external"> following Unity's documentation </a>. For Android, you will need to create a plugin or use a 3rd party asset to retrieve the push token and pass to the SDK. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SetAdvertisingIdentifier (iOS only) </p> </td> 
   <td colname="col2"> <p> Sets the variable meant to hold IDFA in the SDK. IDFA will be sent in lifecycle if it has been set in the SDK. It can also be accessed in Signals (Postbacks). </p> <p> <p>Important:  The SDK will not retrieve the IDFA from the device — you are responsible for retrieving this value from the device and passing it to the SDK. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetAdvertisingIdentifier(string&amp;nbsp;idfa) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetAdvertisingIdentifier&amp;nbsp;("deviceIdfaString"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SubmitAdvertisingIdentifierTask (Android only) </p> </td> 
   <td colname="col2"> <p> Allows you to set the Advertising Identifier (ADID) in your Android App. If you call this method in OnEnable of your first scene before the <span class="codeph"> ADBMobile.CollectLifecycle() </span> method, the ADID you supply will be included in the lifecycle hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SubmitAdvertisingIdentifierTask(&amp;nbsp;SubmitAdIdCallable&amp;nbsp;task) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [MonoPInvokeCallback(typeof(SubmitAdIdCallable))] 
     
public&nbsp;static&nbsp;string&nbsp;HandleSubmitAdIdCallable() 
     
{ 
     
&nbsp;&nbsp;&nbsp;//&nbsp;Write&nbsp;Code&nbsp;to&nbsp;return&nbsp;Adid 
     
&nbsp;&nbsp;&nbsp;return&nbsp;@"GoogleAdid"; 
     
} 
     
&nbsp; 
     
void&nbsp;OnEnable()&nbsp; 
     
{ 
     
&nbsp;&nbsp;ADBMobile.SubmitAdvertisingIdentifierTask&nbsp;(HandleSubmitAdIdCallable); 
     
&nbsp;&nbsp;&nbsp;... 
     
} 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Analytics Methods {#section_41B77EF12BD04C1DA31137C56A1BA909}

<table id="table_2F7497FA7107423A913B7EAE87387866"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> GetTrackingIdentifier </p> </td> 
   <td colname="col2"> <p>Retrieves the analytics tracking identifier. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;GetTrackingIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;trackingId&amp;nbsp;=&amp;nbsp;ADBMobile.GetTrackingIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackState </p> </td> 
   <td colname="col2"> <p>Tracks an app state with optional context data. States are the views that are available in your app, such as "title screen", "level 1", "pause", and so on. These states are similar to pages on a website, and <span class="codeph"> TrackState </span> calls increment page views. </p> <p>If state is empty, it displays as <span class="term"> app name app version (build) </span> in reports. If you see this value in reports, make sure you are setting state in each <span class="codeph"> TrackState </span> call. </p> <p> <b>Note</b>: This is the only tracking call that increments page views. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackState(string&amp;nbsp;state,&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;contextData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;object&gt;); 
     
contextData.Add&nbsp;("user",&nbsp;"jim"); 
     
ADBMobile.TrackState("title&nbsp;screen",&nbsp;contextData);

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackAction </p> </td> 
   <td colname="col2"> <p>Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as "deaths", "level gained", "feed subscriptions", and other metrics. </p> <p> <b>Note</b>: If you have code that might run while the app is in the background (for example, a background data retrieval), use <span class="codeph"> trackActionFromBackground </span> instead. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackAction(string&amp;nbsp;action,&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackAction("level&amp;nbsp;gained",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackActionFromBackground (iOS only) </p> </td> 
   <td colname="col2"> <p>Tracks an action that occurred in the background. This suppresses lifecycle events from firing in certain scenarios. </p> <p> <b>Note</b>: This method should only be called in code that runs while your app is in the background. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackActionFromBackground(string&amp;nbsp;action,&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackActionFromBackground("majorLocationChange",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackLocation </p> </td> 
   <td colname="col2"> <p>Sends the current latitude and longitude coordinates. Also uses points of interest defined in the ADBMobileConfig.json file to determine if the location provided as a parameter is within any of your POI. If the current coordinates are within a defined POI, a context data variable is populated and sent with the TrackLocation call. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLocation(float&amp;nbsp;latValue,&amp;nbsp;float&amp;nbsp;lonValue,&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackLocation(28.418649,&amp;nbsp;-81.581324,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackBeacon (Android only) </p> </td> 
   <td colname="col2"> <p>Sends data identifiying a Beacon which has been ranged by your app. </p> <p> <p>Note:  This method is now Android only due to changes in iOS 10 restricting KVO operations on read-only properties. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackBeacon(int&amp;nbsp;major,&amp;nbsp;int&amp;nbsp;minor,&amp;nbsp;string&amp;nbsp;uuid,&amp;nbsp;ADBBeaconProximity&amp;nbsp;proximity,&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackBeacon&amp;nbsp;(1,&amp;nbsp;2,&amp;nbsp;"2d83ad40-a346-11e4-9dc0-0002a5d5c51b",&amp;nbsp;ADBMobile.ADBBeaconProximity.PROXIMITY_FAR,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackingClearCurrentBeacon (Android only) </p> </td> 
   <td colname="col2"> <p> Clears beacons data after a user leaves the proximity of the beacon. </p> <p> <p>Note:  This method is now Android only due to changes in iOS 10 restricting KVO operations on read-only properties. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingClearCurrentBeacon(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackingClearCurrentBeacon(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackLifetimeValueIncrease </p> </td> 
   <td colname="col2"> <p>Adds amount to the user's lifetime value. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLifetimeValueIncrease(double&amp;nbsp;amount,&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackLifetimeValueIncrease(5,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackTimedActionStart </p> </td> 
   <td colname="col2"> <p>Start a timed action with name action. </p> <p>If you call this method for an action that has already started, the previous timed action is overwritten. </p> <p> <b>Note</b>: This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionStart(string&amp;nbsp;action,&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackTimedActionStart("level2",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackTimedActionUpdate </p> </td> 
   <td colname="col2"> <p>Pass in data to update the context data associated with the given action. </p> <p>The data passed in is appended to the existing data for the given action, and overwrites the data if the same key is already defined for action. </p> <p> <b>Note</b>: This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionUpdate(string&amp;nbsp;action,&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;contextData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;object&gt;(); 
     
&nbsp;contextData.Add("checkpoint",&nbsp;"1:32"); 
     
&nbsp;ADBMobile.TrackTimedActionUpdate("level2",&nbsp;contextData);

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackTimedActionEnd </p> </td> 
   <td colname="col2"> <p>End a timed action. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionEnd(string&amp;nbsp;action); 
    </codeblock> 
    <codeblock class="syntax c">
      ADBMobile.TrackTimedActionEnd("level2"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackingTimedActionExists </p> </td> 
   <td colname="col2"> <p>Returns whether or not a timed action is in progress. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;bool&amp;nbsp;TrackingTimedActionExists(string&amp;nbsp;action); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;level2InProgress&amp;nbsp;=&amp;nbsp;ADBMobile.TrackingTimedActionExists("level2"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackingSendQueuedHits </p> </td> 
   <td colname="col2"> <p>Forces the library to send all hits in the offline queue no matter how many are currently queued. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingSendQueuedHits(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackingSendQueuedHits(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackingClearQueue </p> </td> 
   <td colname="col2"> <p>Clears all hits from the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingClearQueue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackingClearQueue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackingGetQueueSize </p> </td> 
   <td colname="col2"> <p>Retrieves the number of hits currently in the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;int&amp;nbsp;TrackingGetQueueSize(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;queueSize&amp;nbsp;=&amp;nbsp;ADBMobile.TrackingGetQueueSize(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackAdobeDeepLink </p> </td> 
   <td colname="col2"> <p> Tracks an Adobe Deep Link click-through. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackAdobeDeepLink&amp;nbsp;(string&amp;nbsp;url) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackAdobeDeepLink&amp;nbsp;(url); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackPushNotificationClickThrough </p> <p>(For iOS Only) </p> </td> 
   <td colname="col2"> <p> Tracks a push message click-through. This method does not increment page views. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackPushNotificationClickThrough(Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;userInfo)&amp;nbsp; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackPushNotificationClickThrough(&amp;nbsp;userInfo&amp;nbsp;); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackLocalNotificationClickthrough </p> <p> (For iOS Only) </p> </td> 
   <td colname="col2"> <p> Tracks a push message click-through. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLocalNotificationClickthrough(Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;userInfo) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackLocalNotificationClickthrough(&amp;nbsp;userInfo&amp;nbsp;); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Target Methods {#section_D3C17332DD594C3BB4A827B2A35FC4DC}

<table id="table_ADA4523ED0184F7CB882EE95FAAA69D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> TargetLoadRequest </p> </td> 
   <td colname="col2"> <p> Sends a request to your configured Target server and returns the string value of the offer generated in a block callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&nbsp;static&nbsp;void&nbsp;TargetLoadRequest(string&nbsp;name,&nbsp;string&nbsp;defaultContent,&nbsp; 
     
Dictionary&lt;string,&nbsp;object&gt;&nbsp;profileParameters,&nbsp; 
     
Dictionary&lt;string,&nbsp;object&gt;&nbsp;orderParameters,&nbsp; 
     
Dictionary&lt;string,&nbsp;object&gt;&nbsp;mboxParameters,&nbsp; 
     
Dictionary&lt;string,&nbsp;object&gt;&nbsp;requestLocationParameters,&nbsp; 
     
&nbsp;AdobeTargetCallback&nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      [MonoPInvokeCallback(typeof(AdobeTargetCallback))] 
     
public&nbsp;static&nbsp;void&nbsp;HandleAdobeTargetCallback(string&nbsp;content)&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_targetContent&nbsp;=&nbsp;content; 
     
&nbsp;&nbsp;&nbsp;&nbsp;} 
     
ADBMobile.TargetLoadRequest&nbsp;("unityTest",&nbsp;"someDefaultContent",&nbsp;null,&nbsp;null,&nbsp;null,&nbsp;null,&nbsp;HandleAdobeTargetCallback); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TargetGetThirdPartyId </p> </td> 
   <td colname="col2"> <p> Returns the third-party ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;TargetGetThirdPartyId() 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;thirdPartyId&amp;nbsp;=ADBMobile.TargetGetThirdPartyId&amp;nbsp;(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TargetSetThirdPartyId </p> </td> 
   <td colname="col2"> <p> Sets the third-party ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TargetSetThirdPartyId(string&amp;nbsp;thirdPartyId) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TargetSetThirdPartyId("SomeID"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TargetClearCookies </p> </td> 
   <td colname="col2"> <p> Clears any target cookies from your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TargetClearCookies() 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TargetClearCookies&amp;nbsp;(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TargetGetPcId </p> </td> 
   <td colname="col2"> <p> Returns the pcID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;TargetGetPcId() 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;pcID&amp;nbsp;=&amp;nbsp;ADBMobile.TargetGetPcId&amp;nbsp;(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TargetGetSessionId </p> </td> 
   <td colname="col2"> <p> Returns the session ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;TargetGetSessionId() 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;sessionId&amp;nbsp;=&amp;nbsp;ADBMobile.TargetGetSessionId&amp;nbsp;();&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Acquisition Methods {#section_24806720DFAC405FBA1477D535A26BDB}

<table id="table_84E9C846DD064AEFA4C9B2278D260DF2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> AcquisitionCampaignStartForApp </p> </td> 
   <td colname="col2"> <p> Allows developers to start an app acquisition campaign as if the user had clicked a link. This is helpful for creating manual acquisition links and handling the app store redirect yourself. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AcquisitionCampaignStartForApp(string&amp;nbsp;appID,&amp;nbsp;Dictionary&amp;nbsp;&lt;string,&amp;nbsp;object&gt;&amp;nbsp;data) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;contextData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;object&gt;&nbsp;(); 
     
contextData.Add&nbsp;("customKey",&nbsp;"Value"); 
     
ADBMobile.AcquisitionCampaignStartForApp&nbsp;("&nbsp;&nbsp;0652024f-adcd-49f9-9bd7-2552a4564d2f",&nbsp;contextData); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager Methods {#section_01154BB8A64441FA8697B84363C426F6}

<table id="table_EF8799A9296D45258E4AA1098861B006"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> AudienceSubmitSignal </p> </td> 
   <td colname="col2"> <p> Sends audience management a signal with traits and get the matching segments returned in a block callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AudienceSubmitSignal(Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;data,&amp;nbsp;AdobeAudienceManagerCallback&amp;nbsp;callback) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      public&nbsp;static&nbsp;string&nbsp;_aamProfile&nbsp;=&nbsp;""; 
     
[MonoPInvokeCallback(typeof(AdobeAudienceManagerCallback))] 
     
&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;static&nbsp;void&nbsp;HandleAdobeAudienceManagerCallback(string&nbsp;profile) 
     
&nbsp;&nbsp;&nbsp;&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;_aamProfile&nbsp;=&nbsp;profile; 
     
&nbsp;&nbsp;&nbsp;&nbsp;} 
     
var&nbsp;aamTraits&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;object&gt;&nbsp;(); 
     
&nbsp;aamTraits.Add&nbsp;("trait",&nbsp;"b"); 
     
ADBMobile.AudienceSubmitSignal&nbsp;(traits,&nbsp;HandleAdobeAudienceManagerCallback); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> AudienceGetVistorProfile </p> </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained. Returns nil if no signal has been submitted yet. Visitor profile is saved for easy access across multiple launches of your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;string&amp;nbsp;AudienceGetVistorProfile() 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;visitorProfile&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;object&gt;&nbsp;(); 
     
visitorProfile&nbsp;=&nbsp;ADBMobile.AudienceGetVistorProfile&nbsp;(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> AudienceGetDpid </p> </td> 
   <td colname="col2"> <p> Returns the current DPID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;AudienceGetDpid() 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;dpid&amp;nbsp;=&amp;nbsp;ADBMobile.AudienceGetDpid&amp;nbsp;();&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> AudienceGetDpuuid </p> </td> 
   <td colname="col2"> <p> Returns the current DPUUID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;AudienceGetDpuuid() 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;dpuuid&amp;nbsp;=&amp;nbsp;ADBMobile.AudienceGetDpuuid&amp;nbsp;();&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> AudienceSetDpidAndDpuuid </p> </td> 
   <td colname="col2"> <p> Sets the dpid and dpuuid. If dpid and dpuuid are set, they will be sent with each signal. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AudienceSetDpidAndDpuuid(string&amp;nbsp;dpid,&amp;nbsp;string&amp;nbsp;dpuuid) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.AudienceSetDpidAndDpuuid&amp;nbsp;("myDpid",&amp;nbsp;"myDpuuid"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> AudienceReset </p> </td> 
   <td colname="col2"> <p> Resets the Audience Manager UUID and purges the current visitor profile. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AudienceReset() 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.AudienceReset&amp;nbsp;(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Marketing Cloud ID Methods {#section_AA3825E35DB64748BCA78DBE57F8567D}

<table id="table_AC58031F6DD1419DBC45867338A0477B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> GetMarketingCloudID </p> </td> 
   <td colname="col2"> <p>Retrieves the Marketing Cloud visitor ID from the visitor ID service. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;GetMarketingCloudID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;ADBMobile.GetMarketingCloudID(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorSyncIdentifiers </p> </td> 
   <td colname="col2"> <p>Along with the Marketing Cloud visitor ID, you can set additional customer IDs to associate with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, along with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to setCustomerIDs in the JavaScript library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;VisitorSyncIdentifiers(Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;identifiers); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;ids&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;object&gt;&nbsp;(); 
     
ids.Add&nbsp;("player1",&nbsp;"jimbob"); 
     
ADBMobile.VisitorSyncIdentifiers(ids);

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorSyncIdentifiers </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifiers to the Visitor ID service. Pass in the <span class="codeph"> authenticationState </span> as one of the following values: </p> <p> 
     <ul id="ul_2F9FA7912EA64FC3BE004436FDC7BB00"> 
      <li id="li_F56E4ECFE243423DB1F7261EBA4611D3"> <span class="codeph"> VISITOR_ID_AUTHENTICATION_STATE_UNKNOW </span> </li> 
      <li id="li_C0C038BD79534090BC458B20D110EDE0"> <span class="codeph"> VISITOR_ID_AUTHENTICATION_STATE_AUTHENTICATED </span> </li> 
      <li id="li_069AD43C2B3341F4B5C3073CA476D524"> <span class="codeph"> VISITOR_ID_AUTHENTICATION_STATE_LOGGED_OUT </span> </li> 
     </ul> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;VisitorSyncIdentifiers(Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;identifier,&amp;nbsp;ADBMobileVisitorAuthenticationState&amp;nbsp;visitorState)&amp;nbsp; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;identifiers&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;object&gt;&nbsp;(); 
     
identifiers.Add&nbsp;("idType",&nbsp;"idValue"); 
     
ADBMobile.VisitorSyncIdentifiers&nbsp;(identifiers,ADBMobile.ADBMobileVisitorAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_AUTHENTICATED); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorSyncIdentifiersWithType </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifier type and value to the Visitor ID service. Pass in the <span class="codeph"> authenticationState </span> as one of the following values: </p> <p> 
     <ul id="ul_CC811134066347BB8AD0F840052A7656"> 
      <li id="li_24A74463888446A1BCF7764920939961"> <span class="codeph"> VISITOR_ID_AUTHENTICATION_STATE_UNKNOW </span> </li> 
      <li id="li_680C2ADABF854ECE8034ADF734992DF1"> <span class="codeph"> VISITOR_ID_AUTHENTICATION_STATE_AUTHENTICATED </span> </li> 
      <li id="li_C2D1F1BF76E142D2B9340905B3BFB10F"> <span class="codeph"> VISITOR_ID_AUTHENTICATION_STATE_LOGGED_OUT </span> </li> 
     </ul> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;VisitorSyncIdentifiersWithType&amp;nbsp;(string&amp;nbsp;identifierType,&amp;nbsp;string&amp;nbsp;identifier&amp;nbsp;,&amp;nbsp;ADBMobileVisitorAuthenticationState&amp;nbsp;visitorState) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.VisitorSyncIdentifiersWithType("idType",&amp;nbsp;"idValue",&amp;nbsp;ADBMobile.ADBMobileVisitorAuthenticationState.VISITOR_ID_AUTHENTICATION_STATE_AUTHENTICATED); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorAppendtoURL </p> </td> 
   <td colname="col2"> <p> Appends Adobe visitor data to a URL string for use with the Adobe JavaScript library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;VisitorAppendtoURL&amp;nbsp;(string&amp;nbsp;url) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;urlWithAdobeVisitorInfo&amp;nbsp;=&amp;nbsp;ADBMobile.VisitorAppendtoURL&amp;nbsp;("https://example.com"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorGetIds </p> </td> 
   <td colname="col2"> <p>Retrieves a list of <span class="codeph"> ADBVisitorID </span> objects. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;List&amp;nbsp;&lt;ADBVisitorID&gt;&amp;nbsp;VisitorGetIds() 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      List&amp;nbsp;&lt;ADBVisitorID&gt;&amp;nbsp;VisitorIdsList&amp;nbsp;=&amp;nbsp;ADBMobile.VisitorGetIds&amp;nbsp;(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## PII Methods {#section_E5A5F9A3D5ED477885D0912056316365}

<table id="table_459A7FB80A66481DA6E2DC33D7E5F822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> CollectPII </p> </td> 
   <td colname="col2"> <p> Submits a PII collection request. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;CollectPII&amp;nbsp;(Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;data) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;pii&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;object&gt;&nbsp;(); 
     
pii.Add&nbsp;("PIIKey",&nbsp;"PIIValue"); 
     
ADBMobile.CollectPII&nbsp;(pii); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Classes {#section_FD10EBB361A14C238C4A94325FF42C47}

ADBVisitorID

```
public class ADBVisitorID 
{ 
 public string idType; 
 public string identifier; 
 public ADBMobile.ADBMobileVisitorAuthenticationState authenticationState; 
 
 public ADBVisitorID (string adb_idtype, string adb_identifier, ADBMobile.ADBMobileVisitorAuthenticationState adb_authenticationState); 
}
```

## Enumerations {#section_8AE2BC30E07A4ACDB97244431A865538}

ADBPrivacyStatus

* `MOBILE_PRIVACY_STATUS_OPT_IN` 
* `MOBILE_PRIVACY_STATUS_OPT_OUT` 
* `MOBILE_PRIVACY_STATUS_UNKNOWN`

ADBBeaconProximity

* `PROXIMITY_UNKNOWN` 
* `PROXIMITY_IMMEDIATE` 
* `PROXIMITY_NEAR` 
* `PROXIMITY_FAR`

ADBMobileVisitorAuthenticationState

* `VISITOR_ID_AUTHENTICATION_STATE_UNKNOWN` 
* `VISITOR_ID_AUTHENTICATION_STATE_AUTHENTICATED` 
* `VISITOR_ID_AUTHENTICATION_STATE_LOGGED_OUT`

