---
description: Android methods for Xamarin components for Experience Cloud solutions 4.x SDK.
keywords: Xamarin
seo-description: Android methods for Xamarin components for Experience Cloud solutions 4.x SDK.
seo-title: Android methods
solution: Marketing Cloud,Developer
title: Android methods
uuid: 860af1c4-f57e-4bcb-8308-4e316da9a27b
---

# Android methods{#android-methods}

Android methods for Xamarin components for Experience Cloud solutions 4.x SDK.

## Configuration Methods {#section_405AA09390E346E5BB7B1F4E0F65F51E}

* **DebugLogging**

  Returns the current debug logging preference. The default: false.

  * Here is the syntax for this method:

    ```java
    public static Boolean DebugLogging;
    ```

  * Here is the code sample for this method:

    ```java
    getter: var debuglog = Config.DebugLogging;
    setter: Config.DebugLogging = (Java.Lang.Boolean)true;
    ```

* **LifetimeValue**

  Returns the lifetime value of the current user. 

  * Here is the syntax for this method:

    ```java
    public static BigDecimal LifetimeValue; 
    ```

  * Here is the code sample for this method:

    ```java
     var lifetimeValue = Config.LifetimeValue;
     ```

* **PrivacyStatus**

   Returns the enum representation of the privacy status for current user. 
  * `ADBMobilePrivacyStatus.OptIn` - hits are sent immediately. 
  * `ADBMobilePrivacyStatus.OptOut` - hits are discarded. 
  * `ADBMobilePrivacyStatus.Unknown` - If offline tracking is enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If offline tracking is not enabled, hits are discarded until the privacy status changes to opt in. 
  
   The default value is set in the [ADBMobileConfig.json](/help/android/configuration/json-config/json-config.md) file.

  * Here is the syntax for this method:

    ```java
    public static MobilePrivacyStatus PrivacyStatus; 
    ```

  * Here is the code sample for this method:

    ```java
    getter: var privacyStatus = Config.PrivacyStatus; 
    setter: Config.PrivacyStatus = MobilePrivacyStatus.MobilePrivacyStatusUnknown;
    ```

* **UserIdentifier**

  eturns the custom user identifier if a custom identifier has been set. Returns null if a custom identifier is not set. The default value is `null`.

  * Here is the syntax for this method:

    ```java
    public static UserIdentifier();
    ```
  * Here is the code sample for this method:

    ```java
    getter: var userId = Config.UserIdentifier;
    setter: Config.UserIdentifier = "imBatman";
    ```

* **Version**

  Gets the library version. 

  * Here is the syntax for this method:

    ```java
    public static string Version;
    ```

  * Here is the code sample for this method:

    ```java
    var version = ADBMobile.Version;
    ```

* **PauseCollectingLifecycleData**

  ndicates to the SDK that your app is paused, so that lifecycle metrics are calculated correctly. For example, on pause collects a timestamp to determine previous session length. This also sets a flag so that lifecycle correctly knows that the app did not crash. For more information, see [Lifecycle Metrics](/help/android/metrics.md).

  * Here is the syntax for this method:

    ```java
    public static void PauseCollectingLifecycleData (); 
    ```

  * Here is the code sample for this method:

    ```java
    Config.PauseCollectingLifecycleData();
    ```

* **CollectLifecycleData (Activity activity)**

  (4.2 or later) Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. For more information, see For more information, see [Lifecycle Metrics](/help/android/metrics.md). 

  * Here is the syntax for this method:

    ```java
    public static void collectLifecycleData(Activity activity); 
    ```

  * Here is the code sample for this method:

    ```java
    Config.CollectLifecycleData (this);
    ```

* **CollectLifecycleData (Activity activity)**

  (4.2 or later) Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. For more information, see [Lifecycle Metrics](/help/android/metrics.md).

  * Here is the syntax for this method:

    ```java
    public static void collectLifecycleData(Activity activity, IDictionary<string, Object> context));
    ```

  * Here is the code sample for this method:

    ```java
    IDictionary<string, Java.Lang.Object> context = new Dictionary<string, Java.Lang.Object> ();
    context.Add ("key", "value"); 
    Config.CollectLifecycleData (this, context);
    ```
* **OverrideConfigStream**

  (4.2 or later) Lets you load a different `ADBMobile JSON` config file when the application starts. The different configuration is used until the application is closed. 

  * Here is the syntax for this method:

    ```java
    public static void OverrideConfigStream (Stream stream);
    ```

  * Here is the code sample for this method:

    ```java
    Stream st1 = Assets.Open ("ADBMobileConfig-2.json"); 
    Config.OverrideConfigStream (st1); 
    ```

* **SetLargeIconResourceId(int resourceId)**

  (4.2 or later) Set the large icon that will be used for notifications created by the SDK. This icon will be the primary image shown when the user sees the full notification in the notification center. 

  * Here is the syntax for this method:

  ```java
    public static void SetLargeIconResourceId( int resourceId);
    ```

  * Here is the code sample for this method:

    ```java
    Config.SetLargeIconResourceId(R.drawable.appIcon);
    ```

* **SetSmallIconResourceId(int resourceId)**

  (4.2 or later) Set the small icon that will be used for notifications created by the SDK. This icon will show up in the status bar. This will also be the secondary image shown when the user sees the full notification in the notification center. 

  * Here is the syntax for this method:

    ```java
    public static void SetSmallIconResourceId( int resourceId); 
    ```

  * Here is the code sample for this method:

    ```java
     Config.SetSmallIconResourceId(R.drawable.appIcon);
     ```

## Analytics Methods {#section_63CF636104EF41F790C3E4190D755BBA}

* **TrackingIdentifier**

  Returns the automatically generated ID for Analytics. This is an app-specific unique ID that is generated on initial launch and then stored and used from that point forward. This ID is preserved between app upgrades, and is removed on uninstall. 

  * Here is the syntax for this method:

    ```java
    public static string TrackingIdentifier;
    ```

  * Here is the code sample for this method:

    ```java
    Var trackingId = Analytics.TrackingIdentifier
    ```

* **TrackState**

  Tracks an app state with optional context data. `States` are the views that are available in your app, such as "title screen", "level 1", "pause", and so on. These states are similar to pages on a website, and `TrackState` calls increment page views. If state is empty, it displays as "app name app version (build)" in reports. If you see this value in reports, make sure you are setting state in each `TrackState` call. 
  
  >[!TIP]
  >
  >This is the only tracking call that increments page views. 

  * Here is the syntax for this method:

    ```java
    public static void TrackState (string state, IDictionary<string, Object> cdata); 
    ```

  * Here is the code sample for this method:

    ```java
    var cdata = new Dictionary<string, Java.Lang.Object>(); 
    cdata.Add ("key", (Java.Lang.Object)"value"); 
    Analytics.TrackState ("stateName", (IDictionary<string, 
    Java.Lang.Object>)cdata);
    ```

* **TrackAction**

  Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as "deaths", "level gained", "feed subscriptions", and other metrics. 
  
  >[!TIP]
  >
  >
  >If you have code that might run while the app is in the background (for example, a background data retrieval), use `trackActionFromBackground` instead. 

  * Here is the syntax for this method:

    ```java
    public static void TrackAction(string action, IDictionary<string,Object> cdata); 
    ```

  * Here is the code sample for this method:

    ```java
    var cdata = new Dictionary<string, Java.Lang.Object> (); 
    cdata.Add ("key", (Java.Lang.Object)"value");
    Analytics.TrackAction ("actionName", (IDictionary<string, 
    Java.Lang.Object>)cdata);
    ``` 

* **TrackLocation**

  Sends the current latitude and longitude coordinates. Also uses points of interest defined in the `ADBMobileConfig.json` file to determine if the location provided as a parameter is within any of your POI. If the current coordinates are within a defined POI, a context data variable is populated and sent with the `TrackLocation` call. 

  * Here is the syntax for this method:

    ```java
    public static void TrackLocation(Location location, IDictionary<string, Object> cdata); 
    ```

  * Here is the code sample for this method:

    ```java
     Location loc = new Location(LocationManager.GpsProvider);;
     loc.Latitude = 111; 
     loc.Longitude = 44; 
     loc.Accuracy = 5; 
     Analytics.TrackLocation (loc, null);
     ```

* **TrackBeacon**

  Tracks when a users enters proximity of a beacon.

  * Here is the syntax for this method:

    ```java
    public static void TrackBeacon (string uuid, string major, string minor,  Analytics.BEACON_PROXIMITY prox, IDictionary<string, Object> cdata); 
    ```  
  * Here is the code sample for this method:

    ```java
    Analytics.TrackBeacon ("UUID", "1", "2", Analytics.BEACON_PROXIMITY.ProximityImmediate, null); 
    ```

* **ClearBeacon**

  Clears beacons data after a user leaves the proximity of the beacon. 

  * Here is the syntax for this method:

    ```java
    public static void TrackingClearCurrentBeacon();
    ```

  * Here is the code sample for this method:

    ```java
    Analytics.ClearBeacon(); 
    ```

* **TrackLifetimeValueIncrease**

  Adds amount to the user's lifetime value.

  * Here is the syntax for this method:

    ```java
    public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;TrackLifetimeValueIncrease(double&amp;nbsp;amount,&amp;nbsp;&amp;nbsp;IDictionary&lt;string,&amp;nbsp;Object&gt;&amp;nbsp;&amp;nbsp;cdata); 
    ```

  * Here is the code sample for this method:

    ```java
    Analytics.TrackLifetimeValueIncrease(5,&amp;nbsp;null);
    ```

* **TrackTimedActionStart**

  Start a timed action with name action. If you call this method for an action that has already started, the previous timed action is overwritten.
  
  >[!TIP]
  >
  > This call does not send a hit. 

  * Here is the syntax for this method:

    ```java
    public static void TrackTimedActionStart(string action,IDictionary<string, Object> cdata); 
    ```

  * Here is code sample for this method:

    ```java
    Analytics.TrackTimedActionStart("level2", null);
    ```

* **TrackTimedActionUpdate**

  Pass in data to update the context data associated with the given action. The data passed in is appended to the existing data for the given action, and overwrites the data if the same key is already defined for action. 
  
  >[!TIP]
  >
  >This call does not send a hit. 

  * Here is the syntax for this method:

    ```java

    public static void TrackTimedActionUpdate(string action, IDictionary<string, Object> cdata); 
    ```

  * Here is the code sample for this method:

    ```java
    var updatedData = new Dictionary<string, Java.Lang.Object> (); 
    cdata.Add ("key", (Java.Lang.Object)"value"); 
    &nbsp;Analytics.TrackTimedActionUpdate("level2", updatedData); 
    ```

* **TrackTimedActionEnd**

  End a timed action. 

  * Here is the syntax for this method:

    ```java
    public static void TrackTimedActionEnd(string action,Analytics.ITimedActionBlock block);
    ```

  * Here is the code sample for this method:

    ```java
    Analytics.TrackTimedActionEnd ("level2", new TimedActionBlock()); 
         class TimedActionBlock: Java.Lang.Object, 
    Analytics.ITimedActionBlock{ 
         public Java.Lang.Object Call (long inAppDuration, long 
    totalDuration IDictionary<string, Java.Lang.Object> contextData){ 
         return Java.Lang.Boolean.True; 
      } 
    }
    ```

* **TrackingTimedActionExists**

  Returns whether or not a timed action is in progress.

  * Here is the syntax for this method:

    ```java
    public static bool&amp TrackingTimedActionExists(string action); 
    ```

  * Here is the code sample for this method:

    ```java
    var level2InProgress = Analytics.TrackingTimedActionExists("level2"); 
    ```

* **SendQueuedHits**

  Forces the library to send all hits in the offline queue no matter how many are currently queued.

  * Here is the syntax for this method:

    public static void SendQueuedHits();
    ```

  * Here is the code sample for this method:

    ```java
    Analytics.SendQueuedHits(); 
    ```

* **ClearQueue**

  Clears all hits from the offline queue. 

  * Here is the syntax for this method:

    ```java
    public& static void ClearQueue(); 
    ```

  * Here is the code sample for this method:

    ```java
    Analytics.ClearQueue(); 
    ```

* **QueueSize**

  Retrieves the number of hits currently in the offline queue.

  * Here is the syntax for this method:

    ```java
    public static long QueueSize(); 
    ```

  * Here is the code sample for this method:

    ```java
    var queueSize = Analytics.QueueSize();
    ```

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
   <td colname="col1"> <p>MarketingCloudId </p> </td> 
   <td colname="col2"> <p>Retrieves the Experience Cloud ID from the ID service. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;string&amp;nbsp;MarketingCloudId; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      var&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;Visitor.MarketingCloudId; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SyncIdentifiers </p> </td> 
   <td colname="col2"> <p>With the Experience Cloud ID, you can set additional customer IDs to associate with each visitor. The Visitor API accepts multiple Customer IDs for the same visitor, with a customer type identifier to separate the scope of the different customer IDs. This method corresponds to setCustomerIDs in the JavaScript library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;SyncIdentifiers((IDictionary&lt;string,&amp;nbsp;string&gt;&amp;nbsp;identifiers); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      IDictionary&lt;string,&nbsp;string&gt;&nbsp;ids&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;string&gt;&nbsp;(); 
     
ids.Add&nbsp;("pushID",&nbsp;"value2"); 
     
Visitor.SyncIdentifiers&nbsp;(ids); 
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
   <td colname="col2"> <p>Sends request to your configured Target server and returns the string value of the offer generated in a <span class="codeph"> Action&lt;NSDictionary&gt; </span> callback. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;LoadRequest&amp;nbsp;(TargetLocationRequest&amp;nbsp;request,&amp;nbsp;Target.ITargetCallback&amp;nbsp;callback); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      class&nbsp;TargetBlock:&nbsp;Java.Lang.Object,&nbsp;Target.ITargetCallback{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;Call&nbsp;(Java.Lang.Object&nbsp;content) 
     
&nbsp;&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine&nbsp;(content.ToString()); 
     
&nbsp;&nbsp;} 
     
} 
     
var&nbsp;req&nbsp;=&nbsp;Target.CreateRequest&nbsp;("AndroidTest",&nbsp;"defGal",&nbsp;parameters); 
     
&nbsp;&nbsp;&nbsp;&nbsp;Target.LoadRequest&nbsp;(req,&nbsp;new&nbsp;TargetBlock()); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CreateRequest </p> </td> 
   <td colname="col2"> <p>Convenience constructor to create an <span class="codeph"> ADBTargetLocationRequest </span> object with the given parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax c">
      public&amp;nbsp;static&amp;nbsp;TargetLocationRequest&amp;nbsp;TargetCreateRequest&amp;nbsp;(string&amp;nbsp;name,&amp;nbsp;string&amp;nbsp;defaultContent,&amp;nbsp;IDictionary&lt;string,&amp;nbsp;string&gt;&amp;nbsp;parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;parameters&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;(); 
     
&nbsp;&nbsp;&nbsp;&nbsp;parameters.Add&nbsp;("key1",&nbsp;"value2"); 
     
var&nbsp;req&nbsp;=&nbsp;Target.CreateRequest&nbsp;("AndroidTest",&nbsp;"defGal",&nbsp;parameters); 
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
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;AudienceSetDpidAndDpuuid&amp;nbsp;(string&amp;nbsp;Dpid,&amp;nbsp;String&amp;nbsp;Dpuuid); 
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
      class&nbsp;AudienceManagerCallback:&nbsp;Java.Lang.Object,&nbsp;&nbsp;AudienceManager.IAudienceManagerCallback{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;public&nbsp;void&nbsp;Call&nbsp;(Java.Lang.Object&nbsp;content) 
     
&nbsp;&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;Console.WriteLine&nbsp;(content.ToString()); 
     
&nbsp;&nbsp;} 
     
} 
     
IDictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;traits&nbsp;=&nbsp;new&nbsp;Dictionary&lt;string,&nbsp;Java.Lang.Object&gt;&nbsp;(); 
     
&nbsp;&nbsp;&nbsp;&nbsp;traits.Add&nbsp;("trait",&nbsp;"b");

AudienceManager.SignalWithData&nbsp;(traits,&nbsp;new&nbsp;AudienceManagerCallback()); 
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

## Video {#section_CBCE1951CE204A108AD4CA7BB07C7F98}

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
      MediaSettings&nbsp;settings&nbsp;=&nbsp;Media.SettingsWith&nbsp;("name1",&nbsp;10,&nbsp;"playerName1",&nbsp;"playerID1"); 
     
&nbsp;&nbsp;Media.Open&nbsp;(settings,&nbsp;new&nbsp;MediaCallback()); 
     
&nbsp;&nbsp;class&nbsp;MediaCallback:&nbsp;Java.Lang.Object,&nbsp;&nbsp;&nbsp;Media.IMediaCallback{ 
     
public&nbsp;void&nbsp;Call&nbsp;(Java.Lang.Object&nbsp;content) 
     
{

} 
     
} 
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
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;Track&amp;nbsp;(&amp;nbsp;string&amp;nbsp;name,&amp;nbsp;&amp;nbsp;NSDictionary&amp;nbsp;data); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax c">
      Media.Track&amp;nbsp;(settings.Name,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

