---
description: This section contains information relating to using the Adobe Mobile SDK Xamarin component for iOS.
seo-description: This section contains information relating to using the Adobe Mobile SDK Xamarin component for iOS.
seo-title: Methods, Classes, Enums, and Interfaces for iOS
title: Methods, Classes, Enums, and Interfaces for iOS
uuid: 368a6bd5-dff8-4837-9658-32c15cb14aa1
index: y
internal: n
snippet: y
---

# Methods, Classes, Enums, and Interfaces for iOS{#methods-classes-enums-and-interfaces-for-ios}

This section contains information relating to using the Adobe Mobile SDK Xamarin component for iOS.

## iOS Methods {#concept_6A332BD3CF4A436E852A81A1B72386BD}

These tables provide information about the iOS methods for Xamarin components for Marketing Cloud solutions 4.x SDK.

## Configuration Methods {#section_405AA09390E346E5BB7B1F4E0F65F51E}

<table id="table_8493CC7EBDF647BFACC9B2F94BE951D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>CollectLifecycleData </p> </td> 
   <td colname="col2"> <p>Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=metrics" format="https" scope="external"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;CollectLifecycleData(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.CollectLifecycleData(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DebugLogging </p> </td> 
   <td colname="col2"> <p> Returns the current debug logging preference. Default: false </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;bool&amp;nbsp;DebugLogging(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;debugEnabled&amp;nbsp;=&amp;nbsp;ADBMobile.DebugLogging(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SetDebugLogging </p> </td> 
   <td colname="col2"> <p> Sets the debug logging preference to enabled. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetDebugLogging(bool&amp;nbsp;enabled); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetDebugLogging(true); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LifetimeValue </p> </td> 
   <td colname="col2"> <p>Returns the lifetime value of the current user. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;double&amp;nbsp;LifetimeValue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;lifetimeValue&amp;nbsp;=&amp;nbsp;ADBMobile.LifetimeValue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PrivacyStatus </p> </td> 
   <td colname="col2"> <p> Returns the enum representation of the privacy status for current user. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptIn </span> - hits are sent immediately. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptOut </span> - hits are discarded. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.Unknown </span> - If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. </p> <p>Default: The default value is set in <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/json_config.html" format="https" scope="external"> ADBMobileConfig.json </a> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBPrivacyStatus&amp;nbsp;PrivacyStatus(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;privacyStatus&amp;nbsp;=&amp;nbsp;ADBMobile.PrivacyStatus(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SetPrivacyStatus </p> </td> 
   <td colname="col2"> <p>Sets the privacy status for the current user to status. Set to one of the following values: </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptIn </span> - hits are sent immediately. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptOut </span> - hits are discarded. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.Unknown </span> - If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetPrivacyStatus(ADBPrivacyStatus&amp;nbsp;status) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetPrivacyStatus(ADBMobilePrivacyStatus.OptIn&amp;nbsp;); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>UserIdentifier </p> </td> 
   <td colname="col2"> <p>Returns the custom user identifier if a custom identifier has been set. Returns null if a custom identifier is not set. Default: null </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;UserIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;userId&amp;nbsp;=&amp;nbsp;ADBMobile.UserIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SetUserIdentifier </p> </td> 
   <td colname="col2"> <p>Returns the custom user identifier if a custom identifier has been set. Returns null if a custom identifier is not set. Default: null. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;UserIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetUserIdentifier&amp;nbsp;("customUserIdentifier”); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>GetVersion </p> </td> 
   <td colname="col2"> <p>Gets the library version. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;Version(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;version&amp;nbsp;=&amp;nbsp;ADBMobile.Version(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>KeepLifecycleSessionAlive (iOS only) </p> </td> 
   <td colname="col2"> <p>Indicates to the SDK that your next resume from background should not start a new session, regardless of the value of lifecycle session timeout in your config file. </p> <p> <b>Note</b>: this method is intended to be used for apps that register for notifications while in background and should only be called from your code that runs while your app is in the background. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;KeepLifecycleSessionAlive(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.KeepLifecycleSessionAlive(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SetAdvertisingIdentifier </p> </td> 
   <td colname="col2"> <p> Sets the IDFA in the SDK. IDFA will be sent in lifecycle if it has been set in the SDK. It can also be accessed in Signals (Postbacks). </p> <p> <p>Note:  Retrieve the IDFA from Apple APIs only if you are using an ad service. If you retrieve IDFA and are not using it properly, your app might be rejected. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;&amp;nbsp;SetAdvertisingIdentifier&amp;nbsp;(string&amp;nbsp;identifier); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetAdvertisingIdentifier&amp;nbsp;("deviceAdvertisingIdentifer”); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SetPushIdentifier </p> </td> 
   <td colname="col2"> <p> Sets the device token for push notifications. This method should only be used within the <span class="codeph"> DidRegisterForRemoteNotificationsWithDeviceToken </span> method. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;&amp;nbsp;SetPushIdentifier&amp;nbsp;(NSData&amp;nbsp;deviceToken); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetPushIdentifier&amp;nbsp;(NSData.FromString("pushIdentifier”)); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SetAppGroup </p> </td> 
   <td colname="col2"> <p> Sets the app group. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetAppGroup&amp;nbsp;(string&amp;nbsp;appGroup); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetAppGroup&amp;nbsp;("myAppGroup”); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SetAppExtensionType </p> </td> 
   <td colname="col2"> <p> Configures the Adobe Mobile SDK setting to determine what kind of extension is currently being executed. Set to one of the following values: 
     <ul id="ul_66A380E82B13411D994EFAF96C016D7E"> 
      <li id="li_FEDAE525881749488590BD24076D60A7"> <span class="codeph"> ADBMobileAppExtensionTypeRegular </span> - extension is bundled with a containing app </li> 
      <li id="li_C52885026283406587DB9916636AA27A"> <span class="codeph"> ADBMobileAppExtensionTypeStandAlone </span> - extension is not bundled with containing app </li> 
     </ul> </p> <p> <p>Note:  This method should only be used if your app has an extension or is a stand-alone extension. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetAppExtensionType&amp;nbsp;(ADBMobileAppExtensionType&amp;nbsp;type); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetAppExtensionType&amp;nbsp;(ADBMobileAppExtensionType.Regular); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> InstallTVMLHooks </p> </td> 
   <td colname="col2"> <p> Register Adobe Mobile SDK's to the JSContext of your app. This allows you to call the native methods in the Adobe SDK directly from your JavaScript files. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;InstallTVMLHooks&amp;nbsp;(TVApplicationController&amp;nbsp;tvController); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.InstallTVMLHooks&amp;nbsp;(myTvController); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> RegisterAdobeDataCallback </p> </td> 
   <td colname="col2"> <p> Register a callback block to be invoked with the associated <span class="codeph"> NSDictionary </span> data on a <span class="codeph"> ADBMobileDataEvent </span> triggering event. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;RegisterAdobeDataCallback&amp;nbsp;(Action&lt;ADBMobileDataEvent,&amp;nbsp;NSDictionary&gt;&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.RegisterAdobeDataCallback((adobeMobileDataEvent,&nbsp;callbackData)&nbsp;=&gt;&nbsp; 
     
{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine(callbackData);&nbsp;&nbsp;&nbsp; 
     
});&nbsp;

    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Analytics Methods {#section_63CF636104EF41F790C3E4190D755BBA}

<table id="table_7B0B5547D17F4DF7A3F27265BEA46EDE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>TrackingIdentifier </p> </td> 
   <td colname="col2"> <p>Retrieves the analytics tracking identifier. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;TrackingIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;trackingId&amp;nbsp;=&amp;nbsp;ADBMobile.TrackingIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackState </p> </td> 
   <td colname="col2"> <p>Tracks an app state with optional context data. States are the views that are available in your app, such as "title screen", "level 1", "pause", and so on. These states are similar to pages on a website, and <span class="codeph"> TrackState </span> calls increment page views. </p> <p>If state is empty, it displays as "app name app version (build)" in reports. If you see this value in reports, make sure you are setting state in each <span class="codeph"> TrackState </span> call. </p> <p> <b>Note</b>: This is the only tracking call that increments page views. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackState(string&amp;nbsp;state,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;contextData; 
     
&nbsp;contextData&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject("val"),&nbsp;NSObject.FromObject("key")); 
     
&nbsp;ADBMobile.TrackState("title&nbsp;screen",&nbsp;contextData); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackAction </p> </td> 
   <td colname="col2"> <p>Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as "deaths", "level gained", "feed subscriptions", and other metrics. </p> <p> <b>Note</b>: If you have code that might run while the app is in the background (for example, a background data retrieval), use <span class="codeph"> trackActionFromBackground </span> instead. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackAction(string&amp;nbsp;action,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackAction("level&amp;nbsp;gained",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackActionFromBackground (iOS only) </p> </td> 
   <td colname="col2"> <p>Tracks an action that occurred in the background. This suppresses lifecycle events from firing in certain scenarios. </p> <p> <b>Note</b>: This method should only be called in code that runs while your app is in the background. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackActionFromBackground(string&amp;nbsp;action,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackActionFromBackground("majorLocationChange",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackLocation </p> </td> 
   <td colname="col2"> <p>Sends the current latitude and longitude coordinates. Also uses points of interest defined in the <span class="codeph"> ADBMobileConfig.json </span> file to determine if the location provided as a parameter is within any of your POI. If the current coordinates are within a defined POI, a context data variable is populated and sent with the <span class="codeph"> TrackLocation </span> call. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLocation(CLLocation&amp;nbsp;location,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      CoreLocation.CLLocation&nbsp;l&nbsp;=&nbsp;new&nbsp;CoreLocation.CLLocation&nbsp;(111.111,&nbsp;44.156); 
     
ADBMobile.TrackLocation&nbsp;(l,&nbsp;null);

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackBeacon </p> </td> 
   <td colname="col2"> <p>Tracks when a users enters proximity of a beacon. </p> <p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackBeacon(&amp;nbsp;CLBeacon&amp;nbsp;beacon,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      CoreLocation.CLBeacon&nbsp;beacon&nbsp;=&nbsp;new&nbsp;CoreLocation.CLBeacon&nbsp;(); 
     
ADBMobile.TrackBeacon&nbsp;(beacon,&nbsp;null);

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackingClearCurrentBeacon </p> </td> 
   <td colname="col2"> <p> Clears beacons data after a user leaves the proximity of the beacon. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingClearCurrentBeacon(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackingClearCurrentBeacon(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackLifetimeValueIncrease </p> </td> 
   <td colname="col2"> <p>Adds amount to the user's lifetime value. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLifetimeValueIncrease(double&amp;nbsp;amount,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackLifetimeValueIncrease(5,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackTimedActionStart </p> </td> 
   <td colname="col2"> <p>Start a timed action with name action. </p> <p>If you call this method for an action that has already started, the previous timed action is overwritten. </p> <p> <b>Note</b>: This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionStart(string&amp;nbsp;action,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackTimedActionStart("level2",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackTimedActionUpdate </p> </td> 
   <td colname="col2"> <p>Pass in data to update the context data associated with the given action. </p> <p>The data passed in is appended to the existing data for the given action, and overwrites the data if the same key is already defined for action. </p> <p> <b>Note</b>: This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionUpdate(string&amp;nbsp;action,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;updatedData&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("val2"),&nbsp;NSObject.FromObject&nbsp;("key2")); 
     
&nbsp;ADBMobile.TrackTimedActionUpdate("level2",&nbsp;updatedData); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackTimedActionEnd </p> </td> 
   <td colname="col2"> <p>End a timed action. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionEnd(string&amp;nbsp;action,&amp;nbsp;Func&lt;double,&amp;nbsp;double,&amp;nbsp;NSMutableDictionary,&amp;nbsp;sbyte&gt;&amp;nbsp;block); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackTimedActionEnd&nbsp;("level2",&nbsp;(double&nbsp;arg1,&nbsp;double&nbsp;arg2,&nbsp;NSMutableDictionary&nbsp;arg3)&nbsp;=&gt;&nbsp;{ 
     
return&nbsp;Convert.ToSByte(true); 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackingTimedActionExists </p> </td> 
   <td colname="col2"> <p>Returns whether or not a timed action is in progress. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;bool&amp;nbsp;TrackingTimedActionExists(string&amp;nbsp;action); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackTimedActionEnd&nbsp;("timedAction",&nbsp;(double&nbsp;inAppDuration,&nbsp;double&nbsp;totalDuration,&nbsp;NSMutableDictionary&nbsp;data)&nbsp;=&gt;&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;true; 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackingSendQueuedHits </p> </td> 
   <td colname="col2"> <p>Forces the library to send all hits in the offline queue no matter how many are currently queued. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingSendQueuedHits(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackingSendQueuedHits(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackingClearQueue </p> </td> 
   <td colname="col2"> <p>Clears all hits from the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingClearQueue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackingClearQueue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackingGetQueueSize </p> </td> 
   <td colname="col2"> <p>Retrieves the number of hits currently in the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;int&amp;nbsp;TrackingGetQueueSize(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;queueSize&amp;nbsp;=&amp;nbsp;ADBMobile.TrackingGetQueueSize(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackPushMessageClickthrough </p> </td> 
   <td colname="col2"> <p> Tracks a push message click-through. This method does not increment page views. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackPushMessageClickthrough(NSDictionary&amp;nbsp;userInfo); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      public&nbsp;override&nbsp;void&nbsp;DidReceiveRemoteNotification(UIApplication&nbsp;application,&nbsp;NSDictionary&nbsp;userInfo,&nbsp;Action&lt;UIBackgroundFetchResult&gt;&nbsp;completionHandler) 
     
{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;base.DidReceiveRemoteNotification(application,&nbsp;userInfo,&nbsp;completionHandler);

&nbsp;&nbsp;&nbsp;&nbsp;ADBMobile.TrackPushMessageClickthrough(userInfo);

&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;your&nbsp;code&nbsp;here&nbsp;&nbsp; 
     
}

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackLocalNotificationClickthrough </p> </td> 
   <td colname="col2"> <p> Tracks a local notification click-through. This method does not increment page views. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLocalNotificationClickthrough(NSDictionary&amp;nbsp;userInfo); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackLocalNotificationClickthrough(userInfo); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackAdobeDeepLink </p> </td> 
   <td colname="col2"> <p> Tracks an Adobe Deep Link click-through. </p> <p> <p>Note:  Adobe Link data will be appended to the Lifecycle call if it is a launch event, otherwise an extra call will be sent. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackAdobeDeepLink&amp;nbsp;(NSUrl&amp;nbsp;url); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackAdobeDeepLink(NSUrl.FromString("https://adobe.com")); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Acquisition Methods {#section_633896CE45054BCF8301CA1FD378BE5D}

<table id="table_46AC9901D30146F2BEFD1AFA61226744"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> AcquisitionCampaignStartForApp </p> </td> 
   <td colname="col2"> <p> Allows developers to start an app acquisition campaign as if the user had clicked a link. This is helpful for creating manual acquisition links and handling the app store redirect yourself (such as with an <span class="codeph"> SKStoreProductViewController </span>). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AcquisitionCampaignStartForApp&amp;nbsp;(string&amp;nbsp;appId,&amp;nbsp;NSDictionary&amp;nbsp;data); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.AcquisitionCampaignStartForApp(“myAppIdentifier”,&amp;nbsp;NSDictionary.FromObjectAndKey(NSObject.FromObject("value"),&amp;nbsp;NSObject.FromObject("key"))); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Marketing Cloud ID Methods {#section_157919E46030443DBB5CED60D656AD9F}

<table id="table_4B49BB96CB4C4193AF05B3FE96E21205"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>GetMarketingCloudID </p> </td> 
   <td colname="col2"> <p>Retrieves the Marketing Cloud visitor ID from the visitor ID service. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;GetMarketingCloudID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;ADBMobile.GetMarketingCloudID(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>VisitorSyncIdentifiers </p> </td> 
   <td colname="col2"> <p>Along with the Marketing Cloud visitor ID, you can set additional customer IDs to associate with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, along with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to setCustomerIDs in the JavaScript library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;VisitorSyncIdentifiers(NSDictionary&amp;nbsp;identifiers); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;ids&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value2"),&nbsp;NSObject.FromObject&nbsp;("pushID")); 
     
&nbsp;ADBMobile.VisitorSyncIdentifiers(ids); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorSyncIdentifier </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifiers to the Visitor ID service. Pass in the <span class="codeph"> authState </span> as one of the following values: 
     <ul id="ul_67181A1A1C354904914B3F4C7D112F55"> 
      <li id="li_F47306623ABD4E9AA23DD40D709BAFC0"> <span class="codeph"> ADBMobileVisitorAuthenticationStateUnknown </span> </li> 
      <li id="li_EFB3E37AFF7D40D6BEDB8E0750C61905"> <span class="codeph"> ADBMobileVisitorAuthenticationStateAuthenticated </span> </li> 
      <li id="li_28D3232D94CC46BCA1F0DBF8ACA6C0EE"> <span class="codeph"> ADBMobileVisitorAuthenticationStateLoggedOut </span> </li> 
     </ul> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;VisitorSyncIdentifier&amp;nbsp;(string&amp;nbsp;identifierType,&amp;nbsp;string&amp;nbsp;identifier,&amp;nbsp;ADBMobileVisitorAuthenticationState&amp;nbsp;authState); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.VisitorSyncIdentifier("idType",&amp;nbsp;"identifier0",&amp;nbsp;ADBMobileVisitorAuthenticationState.Authenticated);&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorSyncIdentifiers </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifiers to the Visitor ID service. Pass in the <span class="codeph"> authState </span> as one of the following values: 
     <ul id="ul_210C5AFC3E1D4135928E4892A90AA2C3"> 
      <li id="li_BEA0DD10099E42A3BC5119D445D066FE"> <span class="codeph"> ADBMobileVisitorAuthenticationStateUnknown </span> </li> 
      <li id="li_36EA4AB856CB446CA3CE7428A568F4A9"> <span class="codeph"> ADBMobileVisitorAuthenticationStateAuthenticated </span> </li> 
      <li id="li_4F51001C769E42268FA23597B933F755"> <span class="codeph"> ADBMobileVisitorAuthenticationStateLoggedOut </span> </li> 
     </ul> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;VisitorSyncIdentifiers&amp;nbsp;(NSDictionary&amp;nbsp;identifiers,&amp;nbsp;ADBMobileVisitorAuthenticationState&amp;nbsp;authState);&amp;nbsp; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.VisitorSyncIdentifiers(NSDictionary.FromObjectAndKey(NSObject.FromObject("idValue"),&amp;nbsp;NSObject.FromObject("idKey")),&amp;nbsp;ADBMobileVisitorAuthenticationState.Unknown);&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorGetIDs </p> </td> 
   <td colname="col2"> <p> Retrieves an array of read-only <span class="codeph"> ADBVisitorID </span> objects. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBVisitorID[]&amp;nbsp;VisitorGetIDs&amp;nbsp;();&amp;nbsp; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBVisitorID[]&amp;nbsp;visitorIDs&amp;nbsp;=&amp;nbsp;ADBMobile.VisitorGetIDs(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorAppendToURL </p> </td> 
   <td colname="col2"> <p> Appends visitor identifiers to the given URL. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;NSUrl&amp;nbsp;VisitorAppendToURL(NSUrl&amp;nbsp;url); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSUrl&nbsp;myURL&nbsp;=&nbsp;NSUrl.FromString(“https://someurl.com”); 
     
NSUrl&nbsp;urlWithVisitorIDs&nbsp;=&nbsp;ADBMobile.VisitorAppendToURL(myURL);

    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Target Methods {#section_C1E4121CAF9D43538511D857A1F549A7}

<table id="table_17A32CA5A57845209483D8999CC5C082"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>TargetLoadRequest </p> </td> 
   <td colname="col2"> <p> Sends request to your configured Target server and returns the string value of the offer generated in a <span class="codeph"> Action&lt;NSDictionary&gt; </span> callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TargetLoadRequest&amp;nbsp;(ADBTargetLocationRequest&amp;nbsp;request,&amp;nbsp;Action&lt;NSString&gt;&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;mboxParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("mboxParameterKey"));&nbsp; 
     
NSDictionary&nbsp;orderParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("orderParameterKey"));&nbsp; 
     
NSDictionary&nbsp;profileParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("profileParameterKey"));&nbsp; 
     
ADBMobile.TargetLoadRequest(req,&nbsp;profileParameters,&nbsp;orderParameters,&nbsp;mboxParameters,&nbsp;(context)&nbsp;=&gt;&nbsp; 
     
{&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine&nbsp;(context);&nbsp; 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TargetLoadRequest </p> </td> 
   <td colname="col2"> <p> Sends request to your configured Target server and returns the string value of the offer generated in a <span class="codeph"> Action&lt;NSDictionary&gt; </span> callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TargetLoadRequest&amp;nbsp;(string&amp;nbsp;name,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;NSDictionary&amp;nbsp;profileParameters,&amp;nbsp;NSDictionary&amp;nbsp;orderParameters,&amp;nbsp;NSDictionary&amp;nbsp;mboxParameters,&amp;nbsp;Action&lt;NSString&gt;&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;mboxParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("mboxParameterKey"));&nbsp; 
     
NSDictionary&nbsp;orderParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("orderParameterKey"));&nbsp; 
     
NSDictionary&nbsp;profileParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("profileParameterKey"));&nbsp; 
     
ADBMobile.TargetLoadRequest(req,&nbsp;profileParameters,&nbsp;orderParameters,&nbsp;mboxParameters,&nbsp;(context)&nbsp;=&gt;&nbsp; 
     
{&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine&nbsp;(context);&nbsp; 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TargetLoadRequest </p> </td> 
   <td colname="col2"> <p> Sends request to your configured Target server and returns the string value of the offer generated in a <span class="codeph"> Action&lt;NSDictionary&gt; </span> callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TargetLoadRequest&amp;nbsp;(string&amp;nbsp;name,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;NSDictionary&amp;nbsp;profileParameters,&amp;nbsp;NSDictionary&amp;nbsp;orderParameters,&amp;nbsp;NSDictionary&amp;nbsp;mboxParameters,&amp;nbsp;NSDictionary&amp;nbsp;requestLocationParameters,&amp;nbsp;Action&lt;NSString&gt;&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;mboxParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("mboxParameterKey"));&nbsp; 
     
NSDictionary&nbsp;orderParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("orderParameterKey"));&nbsp; 
     
NSDictionary&nbsp;profileParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("profileParameterKey"));&nbsp; 
     
NSDictionary&nbsp;requestLocationParameters&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value"),&nbsp;NSObject.FromObject&nbsp;("requestLocationParameterKey"));&nbsp; 
     
ADBMobile.TargetLoadRequest(req,&nbsp;profileParameters,&nbsp;orderParameters,&nbsp;mboxParameters,&nbsp;requestLocationParameters,&nbsp;(context)&nbsp;=&gt;&nbsp; 
     
{&nbsp; 
     
&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine&nbsp;(context);&nbsp; 
     
});

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TargetCreateRequest </p> </td> 
   <td colname="col2"> <p> Convenience constructor to create an <span class="codeph"> ADBTargetLocationRequest </span> object with the given parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBTargetLocationRequest&amp;nbsp;ADBTargetLocationRequest&amp;nbsp;TargetCreateRequest&amp;nbsp;(string&amp;nbsp;name,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;NSDictionary&amp;nbsp;parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;dict&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value2"),&nbsp;NSObject.FromObject&nbsp;("key1")); 
     
ADBTargetLocationRequest&nbsp;req&nbsp;=&nbsp;ADBMobile.TargetCreateRequest&nbsp;("iOSTest",&nbsp;"defGal",&nbsp;dict); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TargetCreateOrderConfirmRequest </p> </td> 
   <td colname="col2"> <p> Creates an <span class="codeph"> ADBTargetLocationRequest </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBTargetLocationRequest&amp;nbsp;ADBTargetLocationRequest&amp;nbsp;TargetCreateRequest&amp;nbsp;(string&amp;nbsp;name,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;NSDictionary&amp;nbsp;parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TargetCreateOrderConfirmRequest&amp;nbsp;("myOrder",&amp;nbsp;"12345",&amp;nbsp;"29.41",&amp;nbsp;"cool&amp;nbsp;stuff",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TargetClearCookies </p> </td> 
   <td colname="col2"> <p> Clears any target cookies from your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TargetClearCookies(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TargetClearCookies(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TargetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Returns the third-party ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;TargetThirdPartyID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      String&amp;nbsp;targetThirdPartyID&amp;nbsp;=&amp;nbsp;ADBMobile.TargetThirdPartyID();&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TargetSetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Sets the third-party ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TargetSetThirdPartyID(string&amp;nbsp;thirdPartyID); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TargetSetThirdPartyID(“thirdPartyID”); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TargetPcID </p> </td> 
   <td colname="col2"> <p> Returns the <span class="codeph"> PcID </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;TargetPcID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      string&amp;nbsp;targetPcID&amp;nbsp;=&amp;nbsp;ADBMobile.TargetPcID(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TargetSessionID </p> </td> 
   <td colname="col2"> <p> Returns the <span class="codeph"> SessionID </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;TargetSessionID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      string&amp;nbsp;targetSessionID&amp;nbsp;=&amp;nbsp;ADBMobile.TargetSessionID(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager {#section_862C4202B6294B978DEEBB15C5CD5C01}

<table id="table_2C6EDD39B53F4F31B39119B90AF62100"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>AudienceVisitorProfile </p> </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained. Returns nil if no signal has been submitted yet. Visitor profile is saved in <span class="codeph"> NSUserDefaults </span> for easy access across multiple launches of your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;NSDictionary&amp;nbsp;AudienceVisitorProfile&amp;nbsp;(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&amp;nbsp;profile&amp;nbsp;=&amp;nbsp;ADBMobile.AudienceVisitorProfile(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AudienceDpid </p> </td> 
   <td colname="col2"> <p>Returns the current DPID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;AudienceDpid&amp;nbsp;(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      string&amp;nbsp;currentDpid&amp;nbsp;=&amp;nbsp;ADBMobile.AudienceDpid(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AudienceDpuuid </p> </td> 
   <td colname="col2"> <p>Returns the current DPUUID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;AudienceDpuuid&amp;nbsp;(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      string&amp;nbsp;currentDpuuid&amp;nbsp;=&amp;nbsp;ADBMobile.AudienceDpuuid(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AudienceSetDpidAndDpuuid </p> </td> 
   <td colname="col2"> <p>Sets the dpid and dpuuid. If dpid and dpuuid are set, they will be sent with each signal. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AudienceSetDpidAndDpuuid&amp;nbsp;(string&amp;nbsp;dpid,&amp;nbsp;string&amp;nbsp;dpuuid); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.AudienceSetDpidAndDpuuid&amp;nbsp;("testDppid",&amp;nbsp;"testDpuuid"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AudienceSignalWithData </p> </td> 
   <td colname="col2"> <p> Sends audience management a signal with traits and get the matching segments returned in a <span class="codeph"> Action&lt;NSDictionary&gt; </span> &nbsp;callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AudienceSignalWithData&amp;nbsp;(NSDictionary&amp;nbsp;data,&amp;nbsp;Action&lt;NSDictionary&gt;&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;audienceData&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value2"),&nbsp;NSObject.FromObject&nbsp;("key1")); 
     
ADBMobile.AudienceSignalWithData&nbsp;(audienceData,&nbsp;(context)&nbsp;=&gt;&nbsp;{ 
     
Console.WriteLine&nbsp;(context); 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AudienceReset </p> </td> 
   <td colname="col2"> <p> Resets audience manager UUID and purges current visitor profile. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AudienceReset&amp;nbsp;(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.AudienceReset&amp;nbsp;(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Media {#section_CBCE1951CE204A108AD4CA7BB07C7F98}

More details can be found at [Video Analytics](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=video_qs). 

<table id="table_66ADC5C237DC4D2791A749564197A1CB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>MediaCreateSettings </p> </td> 
   <td colname="col2"> <p> Returns an <span class="codeph"> ADBMediaSettings </span> object with specified parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBMediaSettings&amp;nbsp;MediaCreateSettings&amp;nbsp;([string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;string&amp;nbsp;playerName,&amp;nbsp;string&amp;nbsp;playerID); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMediaSettings&amp;nbsp;settings&amp;nbsp;=&amp;nbsp;ADBMobile.MediaCreateSettings&amp;nbsp;("name1",&amp;nbsp;10,&amp;nbsp;"playerName1",&amp;nbsp;"playerID1"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>MediaAdCreateSettings </p> </td> 
   <td colname="col2"> <p>Returns an <span class="codeph"> ADBMediaSettings </span> object for use with tracking an ad video. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBMediaSettings&amp;nbsp;MediaAdCreateSettings&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;&amp;nbsp;string&amp;nbsp;playerName,&amp;nbsp;&amp;nbsp;string&amp;nbsp;parentName,&amp;nbsp;&amp;nbsp;string&amp;nbsp;parentPod,&amp;nbsp;&amp;nbsp;double&amp;nbsp;parentPodPosition,&amp;nbsp;&amp;nbsp;string&amp;nbsp;CPM); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMediaSettings&amp;nbsp;adSettings&amp;nbsp;=&amp;nbsp;ADBMobile.MediaAdCreateSettings("adName1",&amp;nbsp;2,&amp;nbsp;"playerName1",&amp;nbsp;"name1",&amp;nbsp;"podName1",&amp;nbsp;4,&amp;nbsp;"CPM1"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>MediaOpenWithSettings </p> </td> 
   <td colname="col2"> <p> Opens an <span class="codeph"> ADBMediaSettings </span> object for tracking. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaOpenWithSettings&amp;nbsp;(&amp;nbsp;ADBMediaSettings&amp;nbsp;settings,&amp;nbsp;&amp;nbsp;Action&lt;ADBMediaState&gt;&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMediaSettings&nbsp;settings&nbsp;=&nbsp;ADBMobile.MediaCreateSettings&nbsp;("name1",&nbsp;10,&nbsp;"playerName1",&nbsp;"playerID1"); 
     
ADBMobile.MediaOpenWithSettings&nbsp;(settings,&nbsp;(state)&nbsp;=&gt;&nbsp;{ 
     
Console.WriteLine&nbsp;(state.Name); 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>MediaClose </p> </td> 
   <td colname="col2"> <p>Closes the media item named name. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaClose&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaClose&nbsp;(settings.Name);

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>MediaPlay </p> </td> 
   <td colname="col2"> <p>Plays the media item named name at the given offset (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaPlay&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaPlay&amp;nbsp;(settings.Name,&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>MediaComplete </p> </td> 
   <td colname="col2"> <p> Manually mark the media item as complete at the offset provided (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaComplete&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaComplete&amp;nbsp;(settings.Name,&amp;nbsp;5); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>MediaStop </p> </td> 
   <td colname="col2"> <p>Notifies the media module that the video has been stopped or paused at the given offset. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaStop&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaStop&amp;nbsp;(settings.Name,&amp;nbsp;3); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>MediaClick </p> </td> 
   <td colname="col2"> <p>Notifies the media module that the media item has been clicked. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaClick&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaClick&amp;nbsp;(settings.Name,&amp;nbsp;3); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>MediaTrack </p> </td> 
   <td colname="col2"> <p> Sends a track action call (no page view) for the current media state. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaTrack&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;NSDictionary&amp;nbsp;data); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaTrack&amp;nbsp;(settings.Name,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Classes and Enums {#concept_61399D58CA5E463BAB4AACEDFB57F588}

List of classes and enumerations for use in Unity applications.

## Classes {#section_FD10EBB361A14C238C4A94325FF42C47}

ADBVisitorID

```
public class ADBVisitorID : NSObject 
{ 
 public override IntPtr ClassHandle { 
  get; 
 } 
 
 public ADBVisitorID (); 
 
 public virtual ADBMobileVisitorAuthenticationState AuthenticationState (); 
 
 public virtual string Identifier (); 
 
 public virtual string IdType (); 
} 

```

ADBTargetLocationRequest

```
public class ADBTargetLocationRequest : NSObject 
{ 
 
 public override IntPtr ClassHandle { 
  get; 
 } 
 
 public virtual string DefaultContent { 
  get; 
  set; 
 } 
 
 public virtual string Name { 
  get; 
  set; 
 } 
 
 public virtual NSMutableDictionary Parameters { 
  get; 
  set; 
 } 
 
 public ADBTargetLocationRequest (); 
}
```

ADBMediaState

```
public class ADBMediaState : NSObject 
{ 
 public virtual bool Ad { 
  get; 
  set; 
 } 
 
 public override IntPtr ClassHandle { 
  get; 
 } 
 
 public virtual bool Clicked { 
  get; 
  set; 
 } 
 
 public virtual bool Complete { 
  get; 
  set; 
 } 
 
 public virtual bool EventFirstTime { 
  get; 
  set; 
 } 
 
 public virtual nuint EventType { 
  get; 
  set; 
 } 
 
 public virtual double Length { 
  get; 
  set; 
 } 
 
 public virtual string MediaEvent { 
  get; 
  set; 
 } 
 
 public virtual nuint Milestone { 
  get; 
  set; 
 } 
 
 public virtual string Name { 
  get; 
  set; 
 } 
 
 public virtual double Offset { 
  get; 
  set; 
 } 
 
 public virtual nuint OffsetMilestone { 
  get; 
  set; 
 } 
 
 public virtual NSDate OpenTime { 
  get; 
  set; 
 } 
 
 public virtual double Percent { 
  get; 
  set; 
 } 
 
 public virtual string PlayerName { 
  get; 
  set; 
 } 
 
 public virtual string Segment { 
  get; 
  set; 
 } 
 
 public virtual double SegmentLength { 
  get; 
  set; 
 } 
 
 public virtual nuint SegmentNum { 
  get; 
  set; 
 } 
 
 public virtual double TimePlayed { 
  get; 
  set; 
 } 
 
 public virtual double TimePlayedSinceTrack { 
  get; 
  set; 
 } 
 
 public virtual double Timestamp { 
  get; 
  set; 
 } 
 
 public ADBMediaState (); 
}
```

ADBMediaSettings

```
public class ADBMediaSettings : NSObject 
{ 
 public virtual string Channel { 
  get; 
  set; 
 } 
 
 public override IntPtr ClassHandle { 
  get; 
 } 
 
 public virtual nuint CompleteCloseOffsetThreshold { 
  get; 
  set; 
 } 
 
 public virtual string CPM { 
  get; 
  set; 
 } 
 
 public virtual bool IsMediaAd { 
  get; 
  set; 
 } 
 
 public virtual double Length { 
  get; 
  set; 
 } 
 
 public virtual string Milestones { 
  get; 
  set; 
 } 
 
 public virtual string Name { 
  get; 
  set; 
 } 
 
 public virtual string OffsetMilestones { 
  get; 
  set; 
 } 
 
 public virtual string ParentName { 
  get; 
   
  set; 
 } 
 
 public virtual string ParentPod { 
  get; 
  set; 
 } 
 
 public virtual double ParentPodPosition { 
  get; 
  set; 
 } 
 
 public virtual string PlayerID { 
  get; 
  set; 
 } 
 
 public virtual string PlayerName { 
  get; 
  set; 
 } 
 
 public virtual bool SegmentByMilestones { 
  get; 
  set; 
 } 
 
 public virtual bool SegmentByOffsetMilestones { 
  get; 
  set; 
 } 
 
 public virtual nuint TrackSeconds { 
  get; 
  set; 
 } 
 
 public ADBMediaSettings (); 
}
```

Constants

```
public static class Constants 
{ 
 public static NSString ADBConfigKeyCallbackDeepLink { 
  get; 
 } 
 
 public static NSString ADBTargetParameterCategoryId { 
  get; 
 } 
 
 public static NSString ADBTargetParameterMbox3rdPartyId { 
  get; 
 } 
 
 public static NSString ADBTargetParameterMboxHost { 
  get; 
 } 
 
 public static NSString ADBTargetParameterMboxPageValue { 
  get; 
 } 
 
 public static NSString ADBTargetParameterMboxPc { 
  get; 
 } 
 
 public static NSString ADBTargetParameterMboxSessionId { 
  get; 
 } 
 
 public static NSString ADBTargetParameterOrderId { 
  get; 
 } 
 
 public static NSString ADBTargetParameterOrderTotal { 
  get; 
 } 
 
 public static NSString ADBTargetParameterProductPurchasedId { 
  get; 
 } 
}
```

## Enumerations {#section_8AE2BC30E07A4ACDB97244431A865538}

ADBMobileVisitorAuthenticationState

```
public enum ADBMobileVisitorAuthenticationState : ulong 
{ 
 Unknown, 
 Authenticated, 
 LoggedOut 
}
```

ADBMobilePrivacyStatus

```
public enum ADBMobilePrivacyStatus : ulong 
{ 
 OptIn = 1uL, 
 OptOut, 
 Unknown 
}
```

ADBMobileDataEvent

```
public enum ADBMobileDataEvent : ulong 
{ 
 Lifecycle, 
 AcquisitionInstall, 
 AcquisitionLaunch, 
 DeepLink 
}
```

ADBMobileAppExtensionType

```
public enum ADBMobileAppExtensionType : ulong 
{ 
 Regular, 
 StandAlone 
}
```

