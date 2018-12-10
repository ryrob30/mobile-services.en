---
description: Here is a list of Adobe Analytics methods that are provided by the Android library.
keywords: android;library;mobile;sdk
seo-description: Here is a list of Adobe Analytics methods that are provided by the Android library.
seo-title: Analytics Methods
solution: Marketing Cloud,Analytics
title: Analytics Methods
topic: Developer and implementation
uuid: ac7c640e-9dcc-4724-b561-019cc025d5a7
index: y
internal: n
snippet: y
---

# Analytics Methods{#analytics-methods}

Here is a list of Adobe Analytics methods that are provided by the Android library.

The SDK currently supports multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], [!DNL Audience Manager], and the [!DNL Experience Cloud ID Service]. Methods are prefixed according to the solution, for example, Experience Cloud ID methods are prefixed with `analytics`.

Each of the following methods is used to send data to your Adobe Analytics report suite: 

<table id="table_164CA94BE9BD44E59F60389A6D148DF0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> trackState </td> 
   <td colname="col2"> <p>Tracks an app state with optional context data. </p> <p>States are the views that are available in your app, such as <span class="codeph"> home dashboard </span>, <span class="codeph"> app settings </span>, <span class="codeph"> cart </span>, and so on. These states are similar to pages on a website, and <span class="codeph"> trackState </span> calls increment page views. </p> <p>If <span class="codeph"> state </span> is empty, <span class="codeph"> app name app version (build) </span> is displayed in reports. If you see this value in reports, ensure that you set <span class="codeph"> state </span> in each <span class="codeph"> trackState </span> call. </p> <p> <p>Tip:  This is the only tracking call that increments page views. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;trackState(String&amp;nbsp;state,&amp;nbsp;Map&lt;String,&amp;nbsp;Object&gt;&amp;nbsp;contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Analytics.trackState("loginScreen",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackAction </td> 
   <td colname="col2"> <p>Tracks an action in your app. </p> <p>Actions that you want to measure, such as <span class="codeph"> logons </span>, <span class="codeph"> banner taps </span>, <span class="codeph"> feed subscriptions </span>, and other metrics, that occur in your app. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;trackAction(String&amp;nbsp;state,&amp;nbsp;Map&lt;String,&amp;nbsp;Object&gt;&amp;nbsp;contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Analytics.trackAction("heroBannerTouched",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getTrackingIdentifier </td> 
   <td colname="col2"> <p>Returns the automatically generated visitor identifier for Analytics. </p> <p>This is an app-specific, unique visitor ID that is generated at the initial launch and is stored and used from that point forward. The ID is preserved between app upgrades and is removed when the app is uninstalled. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;String&amp;nbsp;getTrackingIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      String&amp;nbsp;trackingId&amp;nbsp;=&amp;nbsp;Analytics.getTrackingIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLocation </td> 
   <td colname="col2"> <p>Sends the current latitude, longitude, and location in a defined <a href="../location/geo-poi.md#concept_72C6C0F74A264CDCB7474DD6610FB011" format="dita" scope="local"> point of interest </a> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;trackLocation(Location&amp;nbsp;location,&amp;nbsp;Map&lt;String,&amp;nbsp;Object&gt;&amp;nbsp;contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Analytics.trackLocation(userLocation,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLifetime​ValueIncrease </td> 
   <td colname="col2"> <p> Adds <span class="codeph"> amount </span> to the user's lifetime value. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      &amp;nbsp;public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;trackLifetimeValueIncrease(BigDecimal&amp;nbsp;amount,&amp;nbsp;Map&lt;String,&amp;nbsp;Object&gt;&amp;nbsp;contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Analytics.trackLifetimeValueIncrease(new&amp;nbsp;BigDecimal(30),&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackTimed​ActionStart </td> 
   <td colname="col2"> <p>Start a timed action with name <span class="codeph"> action </span>. </p> <p> If you call this method for an action that has already started, the previous timed action is overwritten. </p> <p> <p>Tip:  This call does not send a hit. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;trackTimedActionStart(String&amp;nbsp;action,&amp;nbsp;Map&lt;String,&amp;nbsp;Object&gt;&amp;nbsp;contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Analytics.trackTimedActionStart("cartToCheckout",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackTimed​ActionUpdate </td> 
   <td colname="col2"> <p> Pass in <span class="codeph"> contextData </span> to update the context data that is associated with the <span class="codeph"> action </span>. </p> <p>The <span class="codeph"> data </span> that is passed in is appended to the existing data for the action, and if the same key is already defined for <span class="codeph"> action </span>, overwrites the data. </p> <p> <p>Tip:  This call does not send a hit. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;trackTimedActionUpdate(String&amp;nbsp;action,&amp;nbsp;Map&lt;String,&amp;nbsp;Object&gt;&amp;nbsp;contextData); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      HashMap&nbsp;cdata&nbsp;=&nbsp;new&nbsp;HashMap&lt;String,&nbsp;Object&gt;(); 
     
cdata.put("quantity",&nbsp;3); 
     
Analytics.trackTimedActionUpdate("cartToCheckout",&nbsp;cdata); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackTimed​ActionEnd </td> 
   <td colname="col2"> <p> End a timed action. </p> <p>If you provide <span class="codeph"> block </span>, you can access the final time values and can manipulate <span class="codeph"> data </span> before sending the final hit. </p> <p>Tip:  If you provide <span class="codeph"> block </span>, you must return <span class="codeph"> true </span> to send a hit. Passing <span class="codeph"> null </span> for <span class="codeph"> block </span> sends the final hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;trackTimedActionEnd(String&amp;nbsp;action,&amp;nbsp;TimedActionBlock&lt;Boolean&gt;&amp;nbsp;logic); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Analytics.trackTimedActionEnd("cartToCheckout",&nbsp;new&nbsp;Analytics.TimedActionBlock&lt;Boolean&gt;()&nbsp;{ 
     
&nbsp;@Override 
     
&nbsp;public&nbsp;Boolean&nbsp;call(long&nbsp;inAppDuration,&nbsp;long&nbsp;totalDuration,&nbsp;Map&lt;String,&nbsp;Object&gt;&nbsp;contextData)&nbsp;{ 
     
&nbsp;&nbsp;contextData.put("price",&nbsp;49.95); 
     
&nbsp;&nbsp;return&nbsp;true; 
     
&nbsp;} 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sendQueuedHits </p> </td> 
   <td colname="col2"> <p> <i>Requires SDK 4.1</i> </p> <p>Regardless of how many hits are queued, this method forces the library to send all hits in the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      void&amp;nbsp;sendQueuedHits() 
    </codeblock> <p> <b>Examples:</b> </p> 
    <codeblock class="syntax java">
      Analytics.sendQueuedHits(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>getQueueSize </p> </td> 
   <td colname="col2"> <p>Returns the number of stored tracking calls in the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      long&amp;nbsp;getQueueSize() 
    </codeblock> <p> <b>Examples:</b> </p> 
    <codeblock class="syntax java">
      long&amp;nbsp;queueSize&amp;nbsp;=&amp;nbsp;Analytics.getQueueSize(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clearQueue </p> </td> 
   <td colname="col2"> <p>Clears all of the hits from the offline queue. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      void&amp;nbsp;clearQueue() 
    </codeblock> <p> <b>Examples:</b> </p> 
    <codeblock class="syntax java">
      Analytics.clearQueue(); 
    </codeblock> <p> <p>Warning:  Use caution when manually clearing the queue. This process cannot be reversed. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

