---
description: This section contains information relating to using the Adobe Mobile SDK Xamarin component for Android.
seo-description: This section contains information relating to using the Adobe Mobile SDK Xamarin component for Android.
seo-title: Methods, Classes, Enums, and Interfaces for Android
title: Methods, Classes, Enums, and Interfaces for Android
uuid: 3d2197b2-080c-4a31-aa89-5956b0174e38
index: y
internal: n
snippet: y
---

# Methods, Classes, Enums, and Interfaces for Android{#methods-classes-enums-and-interfaces-for-android}

This section contains information relating to using the Adobe Mobile SDK Xamarin component for Android.

## Android Methods {#concept_8FF1FAB1B7D740BEAF6B3F0B93610563}

The following tables provide information about the Android methods for Xamarin components for Marketing Cloud solutions 4.x SDK .

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
   <td colname="col1"> <p>SetContext </p> </td> 
   <td colname="col2"> <p> Sets the current application context. This method should be called in the <span class="codeph"> OnCreate() </span> method of your main activity. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetContext(Context&amp;nbsp;context); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      setter:&amp;nbsp;&amp;nbsp;Config.SetContext(Application.Context); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DebugLogging </p> </td> 
   <td colname="col2"> <p> Returns the current debug logging preference. &amp;nbsp;Default: false </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;Boolean&amp;nbsp;DebugLogging; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      getter:&nbsp;&nbsp;var&nbsp;debuglog&nbsp;=&nbsp;Config.DebugLogging;setter:&nbsp;Config.DebugLogging&nbsp;=&nbsp;(Java.Lang.Boolean)true; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LifetimeValue </p> </td> 
   <td colname="col2"> <p>Returns the lifetime value of the current user. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;BigDecimal&amp;nbsp;LifetimeValue; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;lifetimeValue&amp;nbsp;=&amp;nbsp;Config.LifetimeValue; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PrivacyStatus </p> </td> 
   <td colname="col2"> <p> Returns the enum representation of the privacy status for current user. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptIn </span> - hits are sent immediately. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.OptOut </span> - hits are discarded. </p> <p> <span class="codeph"> ADBMobilePrivacyStatus.Unknown </span> - If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. </p> <p>Default: The default value is set in <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/json_config.html" format="https" scope="external"> ADBMobileConfig.json </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;MobilePrivacyStatus&amp;nbsp;PrivacyStatus; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      getter:&nbsp;var&nbsp;privacyStatus&nbsp;=&nbsp;Config.PrivacyStatus;setter:&nbsp;Config.PrivacyStatus&nbsp;=&nbsp;MobilePrivacyStatus.MobilePrivacyStatusUnknown; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>UserIdentifier </p> </td> 
   <td colname="col2"> <p> Returns the custom user identifier if a custom identifier has been set. Returns null if a custom identifier is not set. </p> <p>Default: null </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      &amp;nbsp;public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;UserIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      getter:&nbsp;var&nbsp;userId&nbsp;=&nbsp;Config.UserIdentifier;setter:&nbsp;Config.UserIdentifier&nbsp;=&nbsp;"imBatman"; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Version </p> </td> 
   <td colname="col2"> <p>Gets the library version. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;Version; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;version&amp;nbsp;=&amp;nbsp;ADBMobile.Version; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PauseCollectingLifecycleData </p> </td> 
   <td colname="col2"> <p> </p> <p> Indicates to the SDK that your app is paused, so that lifecycle metrics are calculated correctly. For example, on pause collects a timestamp to determine previous session length. This also sets a flag so that lifecycle correctly knows that the app did not crash. See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=metrics" format="https" scope="external"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;PauseCollectingLifecycleData&amp;nbsp;(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Config.PauseCollectingLifecycleData(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CollectLifecycleData (Activity activity) </p> </td> 
   <td colname="col2"> <p>(4.2 or later) Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=metrics" format="https" scope="external"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;collectLifecycleData(Activity&amp;nbsp;activity); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Config.CollectLifecycleData&amp;nbsp;(this); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CollectLifecycleData (Activity activity) </p> </td> 
   <td colname="col2"> <p>(4.2 or later) Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. See Lifecycle Metrics. Any entries passed into the context parameter will be included in the lifecycle hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;collectLifecycleData(Activity&amp;nbsp;activity,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;context)); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;context&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;();context.Add&nbsp;("key",&nbsp;"value");Config.CollectLifecycleData&nbsp;(this,&nbsp;context); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>OverrideConfigStream </p> </td> 
   <td colname="col2"> <p>(4.2 or later) Lets you load a different <span class="codeph"> ADBMobile JSON </span> Config file when the application starts. The different configuration is used until the application is closed. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;OverrideConfigStream&amp;nbsp;(Stream&amp;nbsp;strem); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Stream&nbsp;st1&nbsp;=&nbsp;Assets.Open&nbsp;("ADBMobileConfig-2.json");Config.OverrideConfigStream&nbsp;(st1); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SetLargeIconResourceId(int resourceId) </p> </td> 
   <td colname="col2"> <p> (4.2 or later) Set the large icon that will be used for notifications created by the SDK. This icon will be the primary image shown when the user sees the full notification in the notification center. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetLargeIconResourceId(&amp;nbsp;int&amp;nbsp;resourceId); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Config.SetLargeIconResourceId(R.drawable.appIcon); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SetSmallIconResourceId(int resourceId) </p> </td> 
   <td colname="col2"> <p>(4.2 or later) Set the small icon that will be used for notifications created by the SDK. This icon will show up in the status bar. This will also be the secondary image shown when the user sees the full notification in the notification center. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetSmallIconResourceId(&amp;nbsp;int&amp;nbsp;resourceId); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Config.SetSmallIconResourceId(R.drawable.appIcon); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SubmitAdvertisingIdentifierTask </p> </td> 
   <td colname="col2"> <p> Provide a <span class="codeph"> ICallable </span> to the SDK that returns the string of the Advertising Identifier returned from Google Play Services. The SDK runs this task on a background thread and sets an internal variable for Advertising Identifier based on the value returned from the Callable. </p> <p> <p>Note:  If you want to use Advertising Identifier in Acquisition or Lifecycle, you must call it before calling <span class="codeph"> Config.CollectLifecycleData() </span>. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SubmitAdvertisingIdentifierTask&amp;nbsp;(ICallable&amp;nbsp;task); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      class&nbsp;AdvertisingIdentifierTask:&nbsp;Java.Lang.Object,&nbsp;Java.Util.Concurrent.ICallable&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Java.Lang.Object&nbsp;ICallable.Call()&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;“DeviceAdvertisingIdentifier”;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;&nbsp;}&nbsp;
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SetPushIdentifier </p> </td> 
   <td colname="col2"> <p> Sets the device token for push notifications. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SetPushIdentifier(&amp;nbsp;int&amp;nbsp;resourceId); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Config.SetPushIdentifier(“pushIdentifier”); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> RegisterAdobeDataCallback </p> </td> 
   <td colname="col2"> <p> Registers an object that implements the <span class="codeph"> IAdobeDataCallback </span> interface. The "call" method will be invoked with a <span class="codeph"> Config.MobileDataEvent </span> and associated data in a <span class="codeph"> IDictionary&lt;string, Java.Lang.Object&gt; </span> for the triggering event. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;RegisterAdobeDataCallback(Config.IAdobeDataCallback&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Config.RegisterAdobeDataCallback&nbsp;(new&nbsp;AdobeDataCallback());&nbsp;class&nbsp;AdobeDataCallback:&nbsp;Java.Lang.Object,&nbsp;Config.IAdobeDataCallback{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;Java.Lang.Object&nbsp;Call&nbsp;(Config.MobileDataEvent&nbsp;event,&nbsp;IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;contextData)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;//&nbsp;your&nbsp;code&nbsp;here&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;}
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> TrackAdobeDeepLink </p> </td> 
   <td colname="col2"> <p> Track an Adobe deep link. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      1.&amp;nbsp;public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackAdobeDeepLink&amp;nbsp;(Uri&amp;nbsp;uri); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Config.TrackAdobeDeepLink(Android.Net.Uri.Parse("&lt;deeplink_url&gt;")); 
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
   <td colname="col2"> <p>Returns the automatically generated visitor identifier for Analytics. This is an app-specific unique visitor id that is generated on initial launch and then stored and used from that point forward. This ID is preserved between app upgrades, and is removed on uninstall. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;TrackingIdentifier; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Var&amp;nbsp;trackingId&amp;nbsp;=&amp;nbsp;Analytics.TrackingIdentifier 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackState </p> </td> 
   <td colname="col2"> <p>Tracks an app state with optional context data. <span class="term"> States </span> are the views that are available in your app, such as "title screen", "level 1", "pause", and so on. These states are similar to pages on a website, and <span class="codeph"> TrackState </span> calls increment page views. </p> <p>If state is empty, it displays as "app name app version (build)" in reports. If you see this value in reports, make sure you are setting state in each <span class="codeph"> TrackState </span> call. </p> <p> <b>Note</b>: This is the only tracking call that increments page views. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackState&amp;nbsp;(string&amp;nbsp;state,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;cdata&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;();cdata.Add&nbsp;("key",&nbsp;(Java.Lang.Object)"value");Analytics.TrackState&nbsp;("stateName",&nbsp;(IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;)cdata); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackAction </p> </td> 
   <td colname="col2"> <p>Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as "deaths", "level gained", "feed subscriptions", and other metrics. </p> <p>Note: If you have code that might run while the app is in the background (for example, a background data retrieval), use <span class="codeph"> trackActionFromBackground </span> instead. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackAction(string&amp;nbsp;action,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;cdata&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;();cdata.Add&nbsp;("key",&nbsp;(Java.Lang.Object)"value");Analytics.TrackAction&nbsp;("actionName",&nbsp;(IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;)cdata); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackLocation </p> </td> 
   <td colname="col2"> <p>Sends the current latitude and longitude coordinates. Also uses points of interest defined in the <span class="codeph"> ADBMobileConfig.json </span> file to determine if the location provided as a parameter is within any of your POI. If the current coordinates are within a defined POI, a context data variable is populated and sent with the <span class="codeph"> TrackLocation </span> call. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLocation(Location&amp;nbsp;location,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Location&nbsp;loc&nbsp;=&nbsp;new&nbsp;Location(LocationManager.GpsProvider);;loc.Latitude&nbsp;=&nbsp;111;loc.Longitude&nbsp;=&nbsp;44;loc.Accuracy&nbsp;=&nbsp;5;Analytics.TrackLocation&nbsp;(loc,&nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackBeacon </p> </td> 
   <td colname="col2"> <p>Tracks when a users enters proximity of a beacon. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackBeacon&amp;nbsp;(string&amp;nbsp;uuid,&amp;nbsp;string&amp;nbsp;major,&amp;nbsp;string&amp;nbsp;minor,&amp;nbsp;Analytics.BEACON_PROXIMITY&amp;nbsp;prox,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Analytics.TrackBeacon&amp;nbsp;("UUID",&amp;nbsp;"1",&amp;nbsp;"2",&amp;nbsp;Analytics.BEACON_PROXIMITY.ProximityImmediate,&amp;nbsp;null);
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ClearBeacon </p> </td> 
   <td colname="col2"> <p>Clears beacons data after a user leaves the proximity of the beacon. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackingClearCurrentBeacon(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Analytics.ClearBeacon(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackLifetimeValueIncrease </p> </td> 
   <td colname="col2"> <p>Adds amount to the user's lifetime value. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLifetimeValueIncrease(double&amp;nbsp;amount,&amp;nbsp;&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Analytics.TrackLifetimeValueIncrease(5,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackTimedActionStart </p> </td> 
   <td colname="col2"> <p>Start a timed action with name action. </p> <p>If you call this method for an action that has already started, the previous timed action is overwritten. </p> <p> <b>Note</b>: This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionStart(string&amp;nbsp;action,&amp;nbsp;&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Analytics.TrackTimedActionStart("level2",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackTimedActionUpdate </p> </td> 
   <td colname="col2"> <p>Pass in data to update the context data associated with the given action. </p> <p>The data passed in is appended to the existing data for the given action, and overwrites the data if the same key is already defined for action. </p> <p> <b>Note</b>: This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionUpdate(string&amp;nbsp;action,&amp;nbsp;&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;&amp;nbsp;cdata); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&nbsp;updatedData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;();cdata.Add&nbsp;("key",&nbsp;(Java.Lang.Object)"value");&nbsp;Analytics.TrackTimedActionUpdate("level2",&nbsp;updatedData); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackTimedActionEnd </p> </td> 
   <td colname="col2"> <p>End a timed action. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackTimedActionEnd(string&amp;nbsp;action,&amp;nbsp;&amp;nbsp;Analytics.ITimedActionBlock&amp;nbsp;block); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Analytics.TrackTimedActionEnd&nbsp;("level2",&nbsp;new&nbsp;TimedActionBlock());&nbsp;&nbsp;&nbsp;&nbsp;class&nbsp;TimedActionBlock:&nbsp;Java.Lang.Object,&nbsp;Analytics.ITimedActionBlock{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;Java.Lang.Object&nbsp;Call&nbsp;(long&nbsp;inAppDuration,&nbsp;long&nbsp;totalDuration,&nbsp;IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;contextData){&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;Java.Lang.Boolean.True;&nbsp;&nbsp;}} 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TrackingTimedActionExists </p> </td> 
   <td colname="col2"> <p>Returns whether or not a timed action is in progress. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;bool&amp;nbsp;TrackingTimedActionExists(string&amp;nbsp;action); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;level2InProgress&amp;nbsp;=&amp;nbsp;Analytics.TrackingTimedActionExists("level2"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SendQueuedHits </p> </td> 
   <td colname="col2"> <p>Forces the library to send all hits in the offline queue no matter how many are currently queued. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SendQueuedHits(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Analytics.SendQueuedHits(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ClearQueue </p> </td> 
   <td colname="col2"> <p>Clears all hits from the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;ClearQueue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Analytics.ClearQueue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>QueueSize </p> </td> 
   <td colname="col2"> <p>Retrieves the number of hits currently in the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;long&amp;nbsp;QueueSize(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;queueSize&amp;nbsp;=&amp;nbsp;Analytics.QueueSize(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Acquisition Methods {#section_4E5CB162D4D44F538C34ABDE6BD731C7}

<table id="table_D8E37F178D8D4008810FDC48EC2AA8C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> AcquisitionCampaignStartForApp </p> </td> 
   <td colname="col2"> <p> Allows developers to start an app acquisition campaign as if the user had clicked a link. This is helpful for creating manual acquisition links and handling the app store redirect yourself. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;CampaignStartForApp&amp;nbsp;(string&amp;nbsp;appId,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;data); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;data&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;();data.Add("key2",&nbsp;"val2");Acquisition.CampaignStartForApp("com.mycompany.myapp",&nbsp;data);&nbsp;
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
   <td colname="col1"> <p>MarketingCloudId </p> </td> 
   <td colname="col2"> <p>Retrieves the Marketing Cloud visitor ID from the visitor ID service. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;MarketingCloudId; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;Visitor.MarketingCloudId; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SyncIdentifiers </p> </td> 
   <td colname="col2"> <p>Along with the Marketing Cloud visitor ID, you can set additional customer IDs to associate with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, along with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to setCustomerIDs in the JavaScript library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SyncIdentifiers((IDictionary&lt;string,&amp;nbsp;string&gt;&amp;nbsp;identifiers); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      IDictionary&lt;string,&nbsp;string&gt;&nbsp;ids&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;string&gt;&nbsp;();ids.Add&nbsp;("pushID",&nbsp;"value2");Visitor.SyncIdentifiers&nbsp;(ids); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SyncIdentifier </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifier type and value to the Visitor ID service. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&nbsp;static&nbsp;void&nbsp;SyncIdentifier&nbsp;(string&nbsp;identifierType,&nbsp;string&nbsp;identifier,&nbsp;VisitorID.VisitorIDAuthenticationState&nbsp;authenticationState);&nbsp;
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Visitor.SyncIdentifier("idType",&nbsp;"identifier",&nbsp;VisitorID.VisitorIDAuthenticationState.VisitorIdAuthenticationStateAuthenticated);&nbsp;
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SyncIdentifiers </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifier type and value to the Visitor ID service </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&nbsp;static&nbsp;void&nbsp;SyncIdentifiers&nbsp;(IDictionary&lt;string,&nbsp;string&gt;&nbsp;identifiers,VisitorID.VisitorIDAuthenticationState&nbsp;authenticationState); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      IDictionary&lt;string,&nbsp;string&gt;&nbsp;ids&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;string&gt;&nbsp;();&nbsp;ids.Add&nbsp;("pushID",&nbsp;"value2");&nbsp;Visitor.SyncIdentifiers&nbsp;(ids,&nbsp;VisitorID.VisitorIDAuthenticationState.VisitorIdAuthenticationStateAuthenticated);
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Identifiers </p> </td> 
   <td colname="col2"> <p> Retrieves a IList of read-only VisitorID objects </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;Ilist&lt;VisitorID&gt;&amp;nbsp;Identifiers; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      IList&lt;VisitorID&gt;&amp;nbsp;visitorIds&amp;nbsp;=&amp;nbsp;Visitor.Identifiers; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> AppendToURL </p> </td> 
   <td colname="col2"> <p> Appends Visitor IDs to the given URL string. </p> <p> <p>Note:  This method can cause a blocking network call. Blocking time is limited to 100ms, but care should still be taken to not call this on time-sensitive threads. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;AppendToURL&amp;nbsp;(string&amp;nbsp;url); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      string&nbsp;myURL&nbsp;=&nbsp;“someurl.com”;string&nbsp;urlWithVisitorIds&nbsp;=&nbsp;Visitor.AppendToURL(myURL);
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
   <td colname="col1"> <p>LoadRequest </p> </td> 
   <td colname="col2"> <p>Sends request to your configured Target server and returns the string value of the offer generated in a <span class="codeph"> Target.ITargetCallback </span> callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;LoadRequest&amp;nbsp;(TargetLocationRequest&amp;nbsp;request,&amp;nbsp;Target.ITargetCallback&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      class&nbsp;TargetBlock:&nbsp;Java.Lang.Object,&nbsp;Target.ITargetCallback{&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;Call&nbsp;(Java.Lang.Object&nbsp;content)&nbsp;&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine&nbsp;(content.ToString());&nbsp;&nbsp;}}var&nbsp;req&nbsp;=&nbsp;Target.CreateRequest&nbsp;("AndroidTest",&nbsp;"defGal",&nbsp;parameters);&nbsp;&nbsp;&nbsp;&nbsp;Target.LoadRequest&nbsp;(req,&nbsp;new&nbsp;TargetBlock()); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LoadRequest </p> </td> 
   <td colname="col2"> <p>Sends request to your configured Target server and returns the string value of the offer generated in a <span class="codeph"> Target.ITargetCallback </span> callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;LoadRequest&amp;nbsp;(string&amp;nbsp;mbox,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;mboxParameters,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;orderParameters,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;profileParameters,&amp;nbsp;Target.ITargetCallback&amp;nbsp;callback);" 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Class&nbsp;TargetBlock:&nbsp;Java.Lang.Object,&nbsp;Target.ITargetCallback&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;Call&nbsp;(Java.Lang.Object&nbsp;content)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine&nbsp;(content.ToString());&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;}&nbsp;IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;mboxData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;();mboxData.Add("mboxParameterKey",&nbsp;"value");IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;orderData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;();orderData.Add("orderParameterKey",&nbsp;"value");IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;profileData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;();profileData.Add("profileParameterKey",&nbsp;"value");Target.LoadRequest("someMbox",&nbsp;"defaultContent",&nbsp;mboxData,&nbsp;orderData,&nbsp;profileData,&nbsp;new&nbsp;TargetBlock());
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LoadRequest </p> </td> 
   <td colname="col2"> <p>Sends request to your configured Target server and returns the string value of the offer generated in a <span class="codeph"> Target.ITargetCallback </span> callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;LoadRequest&amp;nbsp;(string&amp;nbsp;mbox,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;mboxParameters,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;orderParameters,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;profileParameters,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;requestLocationParameters,&amp;nbsp;Target.ITargetCallback&amp;nbsp;callback);" 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Class&nbsp;TargetBlock:&nbsp;Java.Lang.Object,&nbsp;Target.ITargetCallback&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;Call&nbsp;(Java.Lang.Object&nbsp;content)&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine&nbsp;(content.ToString());&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}&nbsp;}&nbsp;IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;mboxData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;();mboxData.Add("mboxParameterKey",&nbsp;"value");IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;orderData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;();orderData.Add("orderParameterKey",&nbsp;"value");IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;profileData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;();profileData.Add("profileParameterKey",&nbsp;"value");IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;requestLocationData&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;();&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;requestLocationData.Add("requestLocationKey",&nbsp;"value");&nbsp;Target.LoadRequest("someMbox",&nbsp;"defaultContent",&nbsp;mboxData,&nbsp;orderData,&nbsp;profileData,&nbsp;new&nbsp;TargetBlock());
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CreateRequest </p> </td> 
   <td colname="col2"> <p>Convenience constructor to create an <span class="codeph"> ADBTargetLocationRequest </span> object with the given parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;TargetLocationRequest&amp;nbsp;TargetCreateRequest&amp;nbsp;(string&amp;nbsp;name,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;string&gt;&amp;nbsp;parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;parameters&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;();&nbsp;&nbsp;&nbsp;&nbsp;parameters.Add&nbsp;("key1",&nbsp;"value2");var&nbsp;req&nbsp;=&nbsp;Target.CreateRequest&nbsp;("AndroidTest",&nbsp;"defGal",&nbsp;parameters); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CreateOrderConfirmRequest </p> </td> 
   <td colname="col2"> <p>Creates an ADBTargetLocationRequest. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;TargetLocationRequest&amp;nbsp;TargetCreateRequest&amp;nbsp;(string&amp;nbsp;name,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;&amp;nbsp;IDictionary&lt;string,&amp;nbsp;string&gt;&amp;nbsp;&amp;nbsp;parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;orderConfirm&amp;nbsp;=&amp;nbsp;Target.CreateOrderConfirmRequest&amp;nbsp;("myOrder",&amp;nbsp;"12345",&amp;nbsp;"29.41",&amp;nbsp;"cool&amp;nbsp;stuff",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ClearCookies </p> </td> 
   <td colname="col2"> <p>Clears any target cookies from your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;ClearCookies(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Target.ClearCookies&amp;nbsp;(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ThirdPartyID </p> </td> 
   <td colname="col2"> <p> Returns the current Target Third Party ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;ThirdPartyID; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      getter:&nbsp;&nbsp;var&nbsp;thirdPartyId&nbsp;=&nbsp;Target.ThirdPartyID;&nbsp;setter:&nbsp;Target.ThirdPartyID&nbsp;=&nbsp;“thirdPartyId”;
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> PcID </p> </td> 
   <td colname="col2"> <p> Returns the current Target PC ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;PcID; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;pcId&amp;nbsp;=&amp;nbsp;Target.PcID;&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> SessionID </p> </td> 
   <td colname="col2"> <p> Returns the current Target Session ID. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;SessionID; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;sessionId&amp;nbsp;=&amp;nbsp;Target.SessionID;&amp;nbsp; 
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
   <td colname="col1"> <p>VisitorProfile </p> </td> 
   <td colname="col2"> <p>Returns the visitor profile that was most recently obtained. Returns nil if no signal has been submitted yet. Visitor profile is saved in <span class="codeph"> NSUserDefaults </span> for easy access across multiple launches of your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;VisitorProfile; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      NSDictionary&amp;nbsp;profile&amp;nbsp;=&amp;nbsp;AudienceManager.VisitorProfile; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dpid </p> </td> 
   <td colname="col2"> <p>Returns the current <span class="codeph"> DPID </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;Dpuuid; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      string&amp;nbsp;currentDpid&amp;nbsp;=&amp;nbsp;AudienceManager.Dpid; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dpuuid </p> </td> 
   <td colname="col2"> <p>Returns the current <span class="codeph"> DPUUID </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;AudienceDpuuid; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      string&amp;nbsp;currentDpuuid&amp;nbsp;=&amp;nbsp;AudienceManager.Dpuuid; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AudienceSetDpidAndDpuuid </p> </td> 
   <td colname="col2"> <p>Sets the <span class="codeph"> dpid </span> and <span class="codeph"> dpuuid </span>. If <span class="codeph"> dpid </span> and <span class="codeph"> dpuuid </span> are set, they will be sent with each signal. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AudienceSetDpidAndDpuuid&amp;nbsp;(string&amp;nbsp;Dpid,&amp;nbsp;string&amp;nbsp;Dpuuid); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      AudienceManager.SetDpidAndDpuuid&amp;nbsp;("testDpid",&amp;nbsp;"testDpuuid"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SignalWithData </p> </td> 
   <td colname="col2"> <p>Sends audience management a signal with traits and get the matching segments returned in a <span class="codeph"> Action&lt;NSDictionary&gt; </span> &nbsp;callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SignalWithData&amp;nbsp;(IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;audienceData,&amp;nbsp;AudienceManager.IAudienceManagerCallback&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      class&nbsp;AudienceManagerCallback:&nbsp;Java.Lang.Object,&nbsp;&nbsp;AudienceManager.IAudienceManagerCallback{&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;Call&nbsp;(Java.Lang.Object&nbsp;content)&nbsp;&nbsp;{&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine&nbsp;(content.ToString());&nbsp;&nbsp;}}IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;traits&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;();&nbsp;&nbsp;&nbsp;&nbsp;traits.Add&nbsp;("trait",&nbsp;"b");AudienceManager.SignalWithData&nbsp;(traits,&nbsp;new&nbsp;AudienceManagerCallback()); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reset </p> </td> 
   <td colname="col2"> <p>Resets audience manager <span class="codeph"> UUID </span> and purges current visitor profile. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;Reset&amp;nbsp;(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      AudienceManager.Reset&amp;nbsp;(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Media {#section_CBCE1951CE204A108AD4CA7BB07C7F98}

More information is available at [here](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=video_qs). 

<table id="table_66ADC5C237DC4D2791A749564197A1CB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>MediaSettings </p> </td> 
   <td colname="col2"> <p>Returns an <span class="codeph"> MediaSettings </span> object with specified parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;MediaSettings&amp;nbsp;SettingsWith&amp;nbsp;(string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;string&amp;nbsp;playerName,&amp;nbsp;string&amp;nbsp;playerID);&amp;nbsp; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      MediaSettings&amp;nbsp;settings&amp;nbsp;=&amp;nbsp;Media.SettingsWith&amp;nbsp;("name1",&amp;nbsp;10,&amp;nbsp;"playerName1",&amp;nbsp;"playerID1"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AdSettingsWith </p> </td> 
   <td colname="col2"> <p>Returns an <span class="codeph"> MediaSettings </span> object for use with tracking an ad video. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;MediaSettings&amp;nbsp;AdSettingsWith&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;&amp;nbsp;double&amp;nbsp;length,&amp;nbsp;&amp;nbsp;string&amp;nbsp;playerName,&amp;nbsp;&amp;nbsp;string&amp;nbsp;parentName,&amp;nbsp;&amp;nbsp;string&amp;nbsp;parentPod,&amp;nbsp;&amp;nbsp;double&amp;nbsp;parentPodPosition,&amp;nbsp;&amp;nbsp;string&amp;nbsp;CPM); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      MediaSettings&amp;nbsp;adSettings&amp;nbsp;=&amp;nbsp;Media.AdSettingsWith&amp;nbsp;("adName1",&amp;nbsp;2,&amp;nbsp;"playerName1",&amp;nbsp;"name1",&amp;nbsp;"podName1",&amp;nbsp;4,&amp;nbsp;"CPM1"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Open </p> </td> 
   <td colname="col2"> <p>Opens an <span class="codeph"> ADBMediaSettings </span> object for tracking. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;Open&amp;nbsp;(MediaSettings&amp;nbsp;settings,&amp;nbsp;Media.IMediaCallback&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      MediaSettings&nbsp;settings&nbsp;=&nbsp;Media.SettingsWith&nbsp;("name1",&nbsp;10,&nbsp;"playerName1",&nbsp;"playerID1");&nbsp;&nbsp;Media.Open&nbsp;(settings,&nbsp;new&nbsp;MediaCallback());&nbsp;&nbsp;class&nbsp;MediaCallback:&nbsp;Java.Lang.Object,&nbsp;&nbsp;&nbsp;Media.IMediaCallback{public&nbsp;void&nbsp;Call&nbsp;(Java.Lang.Object&nbsp;content){}} 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Close </p> </td> 
   <td colname="col2"> <p>Closes the media item named name. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;Close(&amp;nbsp;string&amp;nbsp;name); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Media.Close&amp;nbsp;&amp;nbsp;(settings.Name); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Play </p> </td> 
   <td colname="col2"> <p>Plays the media item named name at the given offset (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;Play&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Media.Play&amp;nbsp;(settings.Name,&amp;nbsp;0); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Complete </p> </td> 
   <td colname="col2"> <p>Manually mark the media item as complete at the offset provided (in seconds). </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;Complete&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Media.Complete&amp;nbsp;(settings.Name,&amp;nbsp;5); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stop </p> </td> 
   <td colname="col2"> <p>Notifies the media module that the video has been stopped or paused at the given offset. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;Stop&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Media.Stop&amp;nbsp;(settings.Name,&amp;nbsp;3); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Click </p> </td> 
   <td colname="col2"> <p>Notifies the media module that the media item has been clicked. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;Click&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;double&amp;nbsp;offset); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Media.Click&amp;nbsp;(settings.Name,&amp;nbsp;3); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Track </p> </td> 
   <td colname="col2"> <p>Sends a track action call (no page view) for the current media state. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;Track&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;data); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Media.Track&amp;nbsp;(settings.Name,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Classes, Enums, and Interfaces {#concept_13EFA06B371346BF96714D7D4207D212}

List of classes and enumerations for use in Unity applications.

## Classes {#section_FD10EBB361A14C238C4A94325FF42C47}

MediaEventType

```
public class MediaEventType : Object 
{ 
 public const int MediaEventTypeClick; 
 
 public const int MediaEventTypeTrack; 
 
 public const int MediaEventTypeStop; 
 
 public const int MediaEventTypeClose; 
 
 public const int MediaEventTypeComplete; 
 
 public const int MediaEventTypeMonitor; 
 
 public const int MediaEventTypePlay; 
 
 public MediaEventType (); 
} 
```

TargetLocationRequest

```
public class TargetLocationRequest : Object 
{ 
 public const string TargetParameterCategoryId = "categoryId"; 
 
 public const string TargetParameterProductPurchaseId = "purchasedProductIds"; 
 
 public const string TargetParameterMbox3rdpartyId = "mbox3rdPartyId"; 
 
 public const string TargetParameterMboxHost = "mboxHost"; 
 
 public const string TargetParameterMboxPageValue = "mboxPageValue"; 
 
 public const string TargetParameterMboxPc = "mboxPC"; 
 
 public const string TargetParameterMboxSessionId = "mboxSession"; 
 
 public const string TargetParameterOrderId = "orderId"; 
 
 public const string TargetParameterOrderTotal = "orderTotal"; 
 
 public string DefaultContent { 
  get; 
  set; 
 } 
 
 public string Name { 
  get; 
  set; 
 } 
 
 public IDictionary Parameters { 
  get; 
  set; 
 } 
} 
```

VisitorID

```
public class VisitorID : Object 
{ 
 public VisitorID.VisitorIDAuthenticationState AuthenticationState { 
  get; 
  set; 
 } 
 
 public string Id { 
  get; 
  set; 
 } 
 
 public string IdOrigin { 
  get; 
  set; 
 } 
 
 public string IdType { 
  get; 
  set; 
 } 
}
```

## Enumerations {#section_8AE2BC30E07A4ACDB97244431A865538}

MobileDataEvent

```
public sealed class MobileDataEvent : Enum 
{ 
 public static Config.MobileDataEvent MobileEventAcquisitionInstall { 
  get; 
 } 
 
 public static Config.MobileDataEvent MobileEventAcquisitionLaunch { 
  get; 
 } 
 
 public static Config.MobileDataEvent MobileEventLifecycle { 
  get; 
 } 
 
 public static Config.MobileDataEvent ValueOf (string p0); 
 
 public static Config.MobileDataEvent[] Values (); 
}
```

MobilePrivacyStatus

```
public sealed class MobilePrivacyStatus : Enum 
{ 
 public static MobilePrivacyStatus MobilePrivacyStatusOptIn { 
  get; 
 } 
 
 public static MobilePrivacyStatus MobilePrivacyStatusOptOut { 
  get; 
 } 
 
 public static MobilePrivacyStatus MobilePrivacyStatusUnknown { 
  get; 
 } 
 
 public static MobilePrivacyStatus ValueOf (string p0); 
 
 public static MobilePrivacyStatus[] Values (); 
} 
```

VisitorIDAuthenticationState

```
public sealed class VisitorIDAuthenticationState : Enum 
{ 
 public static VisitorID.VisitorIDAuthenticationState VisitorIdAuthenticationStateAuthenticated { 
  get; 
 } 
 
 public static VisitorID.VisitorIDAuthenticationState VisitorIdAuthenticationStateLoggedOut { 
  get; 
 } 
 
 public static VisitorID.VisitorIDAuthenticationState VisitorIdAuthenticationStateUnknown { 
  get; 
 } 
 
 public static VisitorID.VisitorIDAuthenticationState ValueOf (string p0); 
 
 public static VisitorID.VisitorIDAuthenticationState[] Values (); 
} 
```

## Interfaces {#section_927E74A9C4D94D259DECF434A93CA204}

IAdobeDataCallback

```
public interface IAdobeDataCallback : IJavaObject, IDisposable 
{ 
 void Call (Config.MobileDataEvent p0, IDictionary<string, Object> p1); 
}
```

ITimedActionBlock

```
public interface ITimedActionBlock : IJavaObject, IDisposable 
{ 
 Object Call (long p0, long p1, IDictionary<string, Object> p2); 
}
```

IAudienceManagerCallback

```
public interface IAudienceManagerCallback : IJavaObject, IDisposable 
{ 
 void Call (Object p0); 
}
```

IMediaCallback

```
public interface IMediaCallback : IJavaObject, IDisposable 
{ 
 void Call (Object p0); 
} 
```

ITargetCallback

```
public interface ITargetCallback : IJavaObject, IDisposable 
{ 
 void Call (Object p0); 
} 
```
