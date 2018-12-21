---
description: iOS methods for Xamarin components for Experience Cloud solutions 4.x SDK.
keywords: Xamarin
seo-description: iOS methods for Xamarin components for Experience Cloud solutions 4.x SDK.
seo-title: iOS methods
solution: Marketing Cloud,Developer
title: iOS methods
uuid: d6a056db-80c1-44d0-970f-c961ad01b0bc
---

# iOS methods{#ios-methods}

iOS methods for Xamarin components for Experience Cloud solutions 4.x SDK.

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
   <td colname="col1"> CollectLifecycleData </td> 
   <td colname="col2"> <p>Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=metrics" format="https" scope="external"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;CollectLifecycleData(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.CollectLifecycleData(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogging </td> 
   <td colname="col2"> <p> Returns the current debug logging preference. Default: false </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;bool&amp;nbsp;DebugLogging(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;debugEnabled&amp;nbsp;=&amp;nbsp;ADBMobile.DebugLogging(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SetDebugLogging </td> 
   <td colname="col2"> <p> Sets the debug logging preference to enabled. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetDebugLogging(bool&amp;nbsp;enabled); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetDebugLogging(true); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LifetimeValue </td> 
   <td colname="col2"> <p>Returns the lifetime value of the current user. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;double&amp;nbsp;LifetimeValue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;lifetimeValue&amp;nbsp;=&amp;nbsp;ADBMobile.LifetimeValue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyStatus </td> 
   <td colname="col2"> <p> Returns the enum representation of the privacy status for current user. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptIn </span> - hits are sent immediately. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptOut </span> - hits are discarded. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.Unknown </span> - If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. </p> <p>Default: The default value is set in <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/json_config.html" format="https" scope="external"> ADBMobileConfig.json </a> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBPrivacyStatus&amp;nbsp;PrivacyStatus(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;privacyStatus&amp;nbsp;=&amp;nbsp;ADBMobile.PrivacyStatus(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SetPrivacyStatus </td> 
   <td colname="col2"> <p>Sets the privacy status for the current user to status. Set to one of the following values: </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptIn </span> - hits are sent immediately. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptOut </span> - hits are discarded. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.Unknown </span> - If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetPrivacyStatus(ADBPrivacyStatus&amp;nbsp;status) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetPrivacyStatus(ADBMobilePrivacyStatus.OptIn&amp;nbsp;); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UserIdentifier </td> 
   <td colname="col2"> <p>Returns the custom user identifier if a custom identifier has been set. Returns null if a custom identifier is not set. Default: null </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;UserIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;userId&amp;nbsp;=&amp;nbsp;ADBMobile.UserIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SetUserIdentifier </td> 
   <td colname="col2"> <p>Returns the custom user identifier if a custom identifier has been set. Returns null if a custom identifier is not set. Default: null. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;UserIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.SetUserIdentifier&amp;nbsp;("customUserIdentifier”); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetVersion </td> 
   <td colname="col2"> <p>Gets the library version. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;Version(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;version&amp;nbsp;=&amp;nbsp;ADBMobile.Version(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> KeepLifecycleSessionAlive (iOS only) </td> 
   <td colname="col2"> <p>Indicates to the SDK that your next resume from background should not start a new session, regardless of the value of lifecycle session timeout in your config file. </p> <p> <b>Note</b>: this method is intended to be used for apps that register for notifications while in background and should only be called from your code that runs while your app is in the background. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;KeepLifecycleSessionAlive(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.KeepLifecycleSessionAlive(); 
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
   <td colname="col1"> TrackingIdentifier </td> 
   <td colname="col2"> <p>Retrieves the analytics tracking identifier. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;TrackingIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;trackingId&amp;nbsp;=&amp;nbsp;ADBMobile.TrackingIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackState </td> 
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
   <td colname="col1"> TrackAction </td> 
   <td colname="col2"> <p>Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as "deaths", "level gained", "feed subscriptions", and other metrics. </p> <p> <b>Note</b>: If you have code that might run while the app is in the background (for example, a background data retrieval), use <span class="codeph"> trackActionFromBackground </span> instead. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackAction(string&amp;nbsp;action,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackAction("level&amp;nbsp;gained",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackActionFromBackground (iOS only) </td> 
   <td colname="col2"> <p>Tracks an action that occurred in the background. This suppresses lifecycle events from firing in certain scenarios. </p> <p> <b>Note</b>: This method should only be called in code that runs while your app is in the background. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackActionFromBackground(string&amp;nbsp;action,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackActionFromBackground("majorLocationChange",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackLocation </td> 
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
   <td colname="col1"> TrackBeacon </td> 
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
   <td colname="col1"> TrackingClearCurrentBeacon </td> 
   <td colname="col2"> <p> Clears beacons data after a user leaves the proximity of the beacon. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingClearCurrentBeacon(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackingClearCurrentBeacon(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackLifetimeValueIncrease </td> 
   <td colname="col2"> <p>Adds amount to the user's lifetime value. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLifetimeValueIncrease(double&amp;nbsp;amount,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackLifetimeValueIncrease(5,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackTimedActionStart </td> 
   <td colname="col2"> <p>Start a timed action with name action. </p> <p>If you call this method for an action that has already started, the previous timed action is overwritten. </p> <p> <b>Note</b>: This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionStart(string&amp;nbsp;action,&amp;nbsp;NSDictionary&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackTimedActionStart("level2",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackTimedActionUpdate </td> 
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
   <td colname="col1"> TrackTimedActionEnd </td> 
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
   <td colname="col1"> TrackingTimedActionExists </td> 
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
   <td colname="col1"> TrackingSendQueuedHits </td> 
   <td colname="col2"> <p>Forces the library to send all hits in the offline queue no matter how many are currently queued. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingSendQueuedHits(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackingSendQueuedHits(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingClearQueue </td> 
   <td colname="col2"> <p>Clears all hits from the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingClearQueue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackingClearQueue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingGetQueueSize </td> 
   <td colname="col2"> <p>Retrieves the number of hits currently in the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;int&amp;nbsp;TrackingGetQueueSize(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;queueSize&amp;nbsp;=&amp;nbsp;ADBMobile.TrackingGetQueueSize(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Experience Cloud ID Methods {#section_157919E46030443DBB5CED60D656AD9F}

<table id="table_4B49BB96CB4C4193AF05B3FE96E21205"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> GetMarketingCloudID </td> 
   <td colname="col2"> <p>Retrieves the Experience Cloud ID from the ID service. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;GetMarketingCloudID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;ADBMobile.GetMarketingCloudID(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VisitorSyncIdentifiers </td> 
   <td colname="col2"> <p>With the Experience Cloud ID, you can set additional customer IDs to associate with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, along with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to setCustomerIDs in the JavaScript library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;VisitorSyncIdentifiers(NSDictionary&amp;nbsp;identifiers); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;ids&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value2"),&nbsp;NSObject.FromObject&nbsp;("pushID")); 
     
&nbsp;ADBMobile.VisitorSyncIdentifiers(ids); 
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
   <td colname="col1"> TargetLoadRequest </td> 
   <td colname="col2"> <p>Sends request to your configured Target server and returns the string value of the offer generated in a <span class="codeph"> Action&lt;NSDictionary&gt; </span> callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TargetLoadRequest&amp;nbsp;(ADBTargetLocationRequest&amp;nbsp;request,&amp;nbsp;Action&lt;NSString&gt;&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&nbsp;dict&nbsp;=&nbsp;NSDictionary.FromObjectAndKey&nbsp;(NSObject.FromObject&nbsp;("value2"),&nbsp;NSObject.FromObject&nbsp;("key1")); 
     
ADBTargetLocationRequest&nbsp;req&nbsp;=&nbsp;ADBMobile.TargetCreateRequest&nbsp;("iOSTest",&nbsp;"defGal",&nbsp;dict); 
     
ADBMobile.TargetLoadRequest(req,&nbsp;&nbsp;(context)&nbsp;=&gt;&nbsp;{ 
     
Console.WriteLine&nbsp;(context); 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TargetCreateRequest </td> 
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
   <td colname="col1"> TargetCreateOrderConfirmRequest </td> 
   <td colname="col2"> <p> Creates an <span class="codeph"> ADBTargetLocationRequest </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBTargetLocationRequest&amp;nbsp;ADBTargetLocationRequest&amp;nbsp;TargetCreateRequest&amp;nbsp;(string&amp;nbsp;name,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;NSDictionary&amp;nbsp;parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TargetCreateOrderConfirmRequest&amp;nbsp;("myOrder",&amp;nbsp;"12345",&amp;nbsp;"29.41",&amp;nbsp;"cool&amp;nbsp;stuff",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TargetClearCookies </td> 
   <td colname="col2"> <p> Clears any target cookies from your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TargetClearCookies(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TargetClearCookies(); 
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
   <td colname="col1"> AudienceVisitorProfile </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained. Returns nil if no signal has been submitted yet. Visitor profile is saved in <span class="codeph"> NSUserDefaults </span> for easy access across multiple launches of your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;NSDictionary&amp;nbsp;AudienceVisitorProfile&amp;nbsp;(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&amp;nbsp;profile&amp;nbsp;=&amp;nbsp;ADBMobile.AudienceVisitorProfile(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AudienceDpid </td> 
   <td colname="col2"> <p>Returns the current DPID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;AudienceDpid&amp;nbsp;(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      string&amp;nbsp;currentDpid&amp;nbsp;=&amp;nbsp;ADBMobile.AudienceDpid(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AudienceDpuuid </td> 
   <td colname="col2"> <p>Returns the current DPUUID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;AudienceDpuuid&amp;nbsp;(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      string&amp;nbsp;currentDpuuid&amp;nbsp;=&amp;nbsp;ADBMobile.AudienceDpuuid(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AudienceSetDpidAndDpuuid </td> 
   <td colname="col2"> <p>Sets the dpid and dpuuid. If dpid and dpuuid are set, they will be sent with each signal. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AudienceSetDpidAndDpuuid&amp;nbsp;(NSDictionary&amp;nbsp;data,&amp;nbsp;Action&lt;NSDictionary&gt;&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.AudienceSetDpidAndDpuuid&amp;nbsp;("testDppid",&amp;nbsp;"testDpuuid"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> AudienceSignalWithData </td> 
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
   <td colname="col1"> AudienceReset </td> 
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

## Video {#section_CBCE1951CE204A108AD4CA7BB07C7F98}

For more information, see [Video Analytics](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=video_qs). 

<table id="table_66ADC5C237DC4D2791A749564197A1CB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> MediaCreateSettings </td> 
   <td colname="col2"> <p> Returns an <span class="codeph"> ADBMediaSettings </span> object with specified parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBMediaSettings&amp;nbsp;MediaCreateSettings&amp;nbsp;([string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;string&amp;nbsp;playerName,&amp;nbsp;string&amp;nbsp;playerID); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMediaSettings&amp;nbsp;settings&amp;nbsp;=&amp;nbsp;ADBMobile.MediaCreateSettings&amp;nbsp;("name1",&amp;nbsp;10,&amp;nbsp;"playerName1",&amp;nbsp;"playerID1"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MediaAdCreateSettings </td> 
   <td colname="col2"> <p>Returns an <span class="codeph"> ADBMediaSettings </span> object for use with tracking an ad video. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;ADBMediaSettings&amp;nbsp;MediaAdCreateSettings&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;&amp;nbsp;string&amp;nbsp;playerName,&amp;nbsp;&amp;nbsp;string&amp;nbsp;parentName,&amp;nbsp;&amp;nbsp;string&amp;nbsp;parentPod,&amp;nbsp;&amp;nbsp;double&amp;nbsp;parentPodPosition,&amp;nbsp;&amp;nbsp;string&amp;nbsp;CPM); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMediaSettings&amp;nbsp;adSettings&amp;nbsp;=&amp;nbsp;ADBMobile.MediaAdCreateSettings("adName1",&amp;nbsp;2,&amp;nbsp;"playerName1",&amp;nbsp;"name1",&amp;nbsp;"podName1",&amp;nbsp;4,&amp;nbsp;"CPM1"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MediaOpenWithSettings </td> 
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
   <td colname="col1"> MediaClose </td> 
   <td colname="col2"> <p>Closes the media item named name. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaClose&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaClose&nbsp;(settings.Name);

    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MediaPlay </td> 
   <td colname="col2"> <p>Plays the media item named name at the given offset (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaPlay&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaPlay&amp;nbsp;(settings.Name,&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MediaComplete </td> 
   <td colname="col2"> <p> Manually mark the media item as complete at the offset provided (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaComplete&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaComplete&amp;nbsp;(settings.Name,&amp;nbsp;5); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MediaStop </td> 
   <td colname="col2"> <p>Notifies the media module that the video has been stopped or paused at the given offset. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaStop&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaStop&amp;nbsp;(settings.Name,&amp;nbsp;3); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MediaClick </td> 
   <td colname="col2"> <p>Notifies the media module that the media item has been clicked. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;MediaClick&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.MediaClick&amp;nbsp;(settings.Name,&amp;nbsp;3); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MediaTrack </td> 
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

