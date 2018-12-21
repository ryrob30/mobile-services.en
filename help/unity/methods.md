---
description: null
keywords: Unity
seo-description: null
seo-title: ADBMobile.cs methods
solution: Marketing Cloud,Developer
title: ADBMobile.cs methods
uuid: af504934-febd-45d9-81e2-2a310f4c65dc
---

# ADBMobile.cs methods{#adbmobile-cs-methods}

 **Configuration Methods** 

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
    </codeblock> </td> 
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
   <td colname="col2"> <p>Gets the library version. </p> <p> <b>Syntax:</b> </p> 
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
 </tbody> 
</table>

**Analytics Methods** 

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
   <td colname="col1"> <p>TrackBeacon </p> </td> 
   <td colname="col2"> <p> Tracks when a users enters proximity of a beacon. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackBeacon(int&amp;nbsp;major,&amp;nbsp;int&amp;nbsp;minor,&amp;nbsp;string&amp;nbsp;uuid,&amp;nbsp;ADBBeaconProximity&amp;nbsp;proximity,&amp;nbsp;Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      ADBMobile.TrackBeacon(1337,&amp;nbsp;4334,"2d83ad40-a346-11e4-9dc0-0002a5d5c51b",&amp;nbsp;ADBMobile.ADBBeaconProximity.PROXIMITY_FAR,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackingClearCurrentBeacon </p> </td> 
   <td colname="col2"> <p> Clears beacons data after a user leaves the proximity of the beacon. </p> <p> <b>Syntax:</b> </p> 
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
 </tbody> 
</table>

**Experience Cloud ID Methods** 

<table id="table_ADA4523ED0184F7CB882EE95FAAA69D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> GetMarketingCloudID </p> </td> 
   <td colname="col2"> <p>Retrieves the Experience Cloud ID from the ID service. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;GetMarketingCloudID(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;ADBMobile.GetMarketingCloudID(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> VisitorSyncIdentifiers </p> </td> 
   <td colname="col2"> <p>With the Experience Cloud ID, you can set additional customer IDs to associate with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, along with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to setCustomerIDs in the JavaScript library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;VisitorSyncIdentifiers(Dictionary&lt;string,&amp;nbsp;object&gt;&amp;nbsp;identifiers); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;ids&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;object&gt;&nbsp;(); 
     
ids.Add&nbsp;("player1",&nbsp;"jimbob"); 
     
ADBMobile.VisitorSyncIdentifiers(ids);

    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

