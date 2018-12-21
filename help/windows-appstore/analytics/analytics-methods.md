---
description: Information to help you use the Windows 8.1 Universal App Store SDK with Adobe Analytics.
seo-description: Information to help you use the Windows 8.1 Universal App Store SDK with Adobe Analytics.
seo-title: Analytics methods
solution: Marketing Cloud,Analytics
title: Analytics methods
topic: Developer and implementation
uuid: 79db105c-216c-4061-97f3-a55954995e67
---

# Analytics methods{#analytics-methods}

Information to help you use the Windows 8.1 Universal App Store SDK with Adobe Analytics.

The SDK currently has support for multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], and [!DNL Audience Manager]. Methods are prefixed according to the solution. Analytics methods are prefixed with "Analytics."

Each of these methods is used to send data into your Adobe Analytics report suite.

>[!NOTE]
>
>When you consume winmd methods from winJS (JavaScript), all methods automatically have their first letter lowercased.

<table id="table_164CA94BE9BD44E59F60389A6D148DF0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> TrackState <p>winJS: trackState </p> </td> 
   <td colname="col2"> <p>Tracks an app state with optional context data. States are the views that are available in your app, such as "home dashboard", "app settings", "cart", and so on. These states are similar to pages on a website, and <span class="codeph"> TrackState </span> calls increment page views. </p> <p>If <span class="codeph"> state </span> is empty, it displays as "app name app version (build)" in reports. If you see this value in reports, make sure you are setting <span class="codeph"> state </span> in each <span class="codeph"> TrackState </span> call. </p> <p>Note:  This is the only tracking call that increments page views. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;TrackState(Platform::String&amp;nbsp;^state,&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
ADB.Analytics.trackState("loginScreen",&nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackAction <p>winJS: trackAction </p> </td> 
   <td colname="col2"> <p>Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as "logons", "banner taps", "feed subscriptions", and other metrics. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;TrackAction(Platform::String&amp;nbsp;^action,&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^contextData);&amp;nbsp;&amp;nbsp;&amp;nbsp; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
ADB.Analytics.trackAction("Button&nbsp;Click",&nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetTrackingIdentifierAsync <p>winJS: getTrackingIdentifierAsync </p> </td> 
   <td colname="col2"> <p>Returns the automatically generated visitor identifier for Analytics. This is an app-specific unique visitor id that is generated on initial launch and then stored and used from that point forward. This ID is preserved between app upgrades, and is removed on uninstall. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Windows::Foundation::IAsyncOperation&lt;Platform::String^&gt;&amp;nbsp;^GetTrackingIdentifierAsync(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;trackingIdentifier; 
     
ADBMobile.Analytics.getTrackingIdentifierAsync().then(function&nbsp;(trackingid)&nbsp;{ 
     
&nbsp;&nbsp;&nbsp;&nbsp;trackingIdentifier&nbsp;=&nbsp;trackingid; 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackLocation <p>winJS: trackLocation </p> </td> 
   <td colname="col2"> <p>Sends the current x y coordinates. Also uses points of interest defined in the <span class="codeph"> ADBMobileConfig.json </span> file to determine if the location provided as a parameter is within any of your POI. If the current coordinates are within a defined POI, a context data variable is populated and sent with the <span class="codeph"> trackLocation </span> call. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;TrackLocation(double&amp;nbsp;lat,&amp;nbsp;double&amp;nbsp;lon,&amp;nbsp;double&amp;nbsp;accuracy,&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
ADB.Analytics.trackLocation(47.60621,&nbsp;-122.33207,&nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackLifetime​ValueIncrease <p>winJS: trackLifetime​ValueIncrease </p> </td> 
   <td colname="col2"> <p> Adds <span class="codeph"> amount </span> to the user's lifetime value. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;TrackLifetimeValueIncrease(float&amp;nbsp;amount,&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
ADB.Analytics.trackLifetimeValueIncrease(10,&nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackTimed​ActionStart <p>winJS: trackTimed​ActionStart </p> </td> 
   <td colname="col2"> <p>Start a timed action with name <span class="codeph"> action </span>. </p> <p> If you call this method for an action that has already started, the previous timed action is overwritten. </p> <p>Note:  This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;TrackTimedActionStart(Platform::String&amp;nbsp;^action,&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
ADB.Analytics.trackTimedActionStart("cartToCheckout",&nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackTimed​ActionUpdate <p>winJS: trackTimed​ActionUpdate </p> </td> 
   <td colname="col2"> <p> Pass in <span class="codeph"> contextData </span> to update the context data associated with the given <span class="codeph"> action </span>. </p> <p>The <span class="codeph"> data </span> passed in is appended to the existing data for the given action, and overwrites the data if the same key is already defined for <span class="codeph"> action </span> . </p> <p>Note:  This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;TrackTimedActionUpdate(Platform::String&amp;nbsp;^action,&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
var&nbsp;contextData&nbsp;=&nbsp;new&nbsp;Windows.Foundation.Collections.PropertySet(); 
     
contextData["quantity"]&nbsp;=&nbsp;3; 
     
ADB.Analytics.trackTimedActionUpdate("cartToCheckout",&nbsp;contextData); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackTimedActionExistsAsync <p>winJS: trackTimedActionExistsAsync </p> </td> 
   <td colname="col2"> <p>Returns true if the given timed action exists, and false if it does not. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Windows::Foundation::IAsyncOperation&lt;bool&gt;&amp;nbsp;^TrackTimedActionExistsAsync(Platform::String&amp;nbsp;^action); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADBMobile.Analytics.trackTimedActionExistsAsync("signUp").then(function&nbsp;(exists)&nbsp;{ 
     
&nbsp;actionExists&nbsp;=&nbsp;exists; 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackTimed​ActionEnd <p>winJS: trackTimed​ActionEnd </p> </td> 
   <td colname="col2"> <p> End a timed action. </p> 
    <!--<p>If you provide <codeph>block</codeph>, you will have access to the final time values and be able to manipulate <codeph>data</codeph> prior to sending the final hit. </p> <note>If you provide <codeph>block</codeph>, you must return true to send a hit. Passing in <codeph>null</codeph> for <codeph>block</codeph> sends the final hit. </note>--> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;TrackTimedActionEnd(Platform::String&amp;nbsp;^action); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
ADB.Analytics.trackTimedActionEnd("cartToCheckout"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClearTrackingQueue <p>winJS: clearTrackingQueue </p> </td> 
   <td colname="col2"> <p>Clears all stored hits from the Analytics tracking queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;ClearTrackingQueue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADBMobile.Analytics.clearTrackingQueue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetQueueSizeAsync <p>winJS: getQueueSizeAsync </p> </td> 
   <td colname="col2"> <p>Returns the number of hits currently stored in the Analytics queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Windows::Foundation::IAsyncOperation&lt;int&gt;&amp;nbsp;^GetQueueSizeAsync(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;queueSize; 
     
ADBMobile.Analytics.getQueueSizeAsync().then(function&nbsp;(size)&nbsp;{ 
     
&nbsp;queueSize&nbsp;=&nbsp;size; 
     
}); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

