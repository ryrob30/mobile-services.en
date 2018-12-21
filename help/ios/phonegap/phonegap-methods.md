---
description: You can use iOS PhoneGap Plug-in Methods to complete a variety of tasks.
keywords: phonegap
seo-description: You can use iOS PhoneGap Plug-in Methods to complete a variety of tasks.
seo-title: PhoneGap Plug-in Methods
solution: Marketing Cloud,Analytics
title: PhoneGap Plug-in Methods
topic: Developer and implementation
uuid: bd830fe5-804a-4d0a-bbb6-99a6d8da6a03
---

# PhoneGap Plug-in Methods{#phonegap-plug-in-methods}

You can use iOS PhoneGap Plug-in Methods to complete a variety of tasks.

Here is a link of the iOS PhoneGap Plug-in methods:

* Configuration 
* Tracking 
* Target 
* Acquisition 
* Audience Manager 
* ID service

In `html` files where you want to use tracking, add the following to the `<head>` tag:

```
<script type="text/javascript" charset="utf-8" src="ADB_Helper.js"></script>
```

This section contains the following information:

* [Configuration Methods](../phonegap/phonegap-methods.md#section_CC429F68292D4601AEEF0A91445E1185) 
* [PII Methods](../phonegap/phonegap-methods.md#section_DB27270D2CEB4D369E0090FD9D1A7F81) 
* [Tracking Methods](../phonegap/phonegap-methods.md#section_7946BB753A4446FE8A3ED728AEF97D04) 
* [Target Methods](../phonegap/phonegap-methods.md#section_C45D2FE54AE04EB5BD24D3508F8A3212) 
* [Acquisition Methods](../phonegap/phonegap-methods.md#section_EDEA25C4B2884487827069E9257A0BA6) 
* [Advertising Identifier](../phonegap/phonegap-methods.md#section_194607D101B047A19C51B19E176E1500) 
* [Audience Manager Methods](../phonegap/phonegap-methods.md#section_1FD12B29A0AF41D3BEACBB3D624EA0E4) 
* [ID Service Methods](../phonegap/phonegap-methods.md#section_840B4FAEA55B466F9754148ABA15EBDA)

## Configuration Methods {#section_CC429F68292D4601AEEF0A91445E1185}

<table id="table_5FAF1815B94C4CEFA4891F70E2BDABBA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Method </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>getPrivacyStatus </p> </td> 
   <td colname="col2"> <p>Returns the privacy status for current user. </p> <p>Here are the available statuses: </p> <p> 
     <ul id="ul_9B1847F75F49466796B5929C485DA9DD"> 
      <li id="li_738965BC048044B5A6ACCE02FC84E74E"> <span class="codeph"> ADB.optedIn </span>, where hits are sent immediately. </li> 
      <li id="li_9BB3A31DC62B4EE6AEC364145463E09B"> <span class="codeph"> ADB.optedOut </span>, where hits are discarded. </li> 
      <li id="li_AF7571F4B2614B8EAAC43F17216626CF"> <span class="codeph"> ADB.optUnknown </span> <p>If your report suite <b>is</b> timestamp-enabled, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded). If your report suite <b>is not</b> timestamp-enabled, hits are discarded until the privacy status changes to opt in. </p> </li> 
     </ul> </p> <p>The default value is set in <span class="codeph"> ADBMobileConfig.json </span> </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      getPrivacyStatus(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;});&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>setPrivacyStatus </p> </td> 
   <td colname="col2"> <p>Sets the privacy status for the current user to <span class="codeph"> status </span>. Set to one of the following values: </p> <p>You can set one of the following statuses: </p> <p> 
     <ul id="ul_17FB8774E8A24E1FB7F8780A814FD7DD"> 
      <li id="li_715F97E56DF2461EB272EDBB49604C95"> <span class="codeph"> ADB.optedIn </span>, where hits are sent immediately. </li> 
      <li id="li_78CFABFB22CC4DF095591DA6040491F6"> <span class="codeph"> ADB.optedOut </span>, where hits are discarded. </li> 
      <li id="li_54E48E4C6FD7423E916F4BF1FD21080F"> <span class="codeph"> ADB.optUnknown </span> <p>If your report suite <b>is</b> timestamp-enabled, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded). If your report suite <b>is not</b> timestamp-enabled, hits are discarded until the privacy status changes to opt in. </p> </li> 
     </ul> </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.setPrivacyStatus('ADB.optedIn'); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>getLifetimeValue </p> </td> 
   <td colname="col2"> <p>Returns the lifetime value of the current user. </p> <p>The default value is 0. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.getLifetimeValue(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;});&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>setDebugLogging </p> </td> 
   <td colname="col2"> <p>Enables ( <span class="codeph"> true </span>) or disables ( <span class="codeph"> false </span>) viewing debug information. By default, this variable is <span class="codeph"> false </span>. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.setDebugLogging(true); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>getVersion </p> </td> 
   <td colname="col2"> <p>Gets the library version. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.getVersion(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;versionNum&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;versionNum&amp;nbsp;=&amp;nbsp;1.0;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackingIdentifier </p> </td> 
   <td colname="col2"> <p>Returns the automatically generated visitor identifier. </p> <p>This is an app-specific unique visitor ID that is generated when the app is initially launched and is stored and used from that point forward. This ID is preserved between app upgrades, and is removed when the app is uninstalled. </p> <p> <p>Tip:  If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous visitor ID (custom or automatically generated) is retrieved and stored as the custom user identifier (see the <span class="codeph"> getUserIdentifier </span> row below). This preserves visitor data between upgrades of the SDK. </p> </p> <p>For new installations on the 4.x SDK, the user identifier is <span class="codeph"> null </span> and tracking identifier is used. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackingIdentifier(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>getUserIdentifier </p> </td> 
   <td colname="col2"> <p>Returns the custom user identifier if a custom identifier has been set, and returns <span class="codeph"> null </span> if a custom identifier has not been set. </p> <p>The default value is <span class="codeph"> null </span>. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      getUserIdentifier(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>setUserIdentifier </p> </td> 
   <td colname="col2"> <p>Sets the user identifier to <span class="codeph"> identifier </span>. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.setUserIdentifier('testUser'); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>setPushIdentifier </p> </td> 
   <td colname="col2"> <p> Sets the device token for push notifications. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.setPushIdentifier(pushIdentifier,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p> </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.setPushIdentifier('test_push_identifier',function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>keepLifecycleSessionAlive </p> </td> 
   <td colname="col2"> <p>Sets the preference of lifecycle session keep alive. </p> <p> <p>Important:  Calling <span class="codeph"> keepLifecycleSessionAlive </span> prevents your app from launching a new session the next time it is resumed from background. You should only use this method if your app registers for notifications in the background. </p> </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.keepLifecycleSessionAlive(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackingSendQueuedHits </p> </td> 
   <td colname="col2"> <p>Forces the library to send all queued hits regardless of current batch options. </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackingSendQueuedHits(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackingGetQueueSize </p> </td> 
   <td colname="col2"> <p>Gets or sets the number of stored tracking calls in the offline queue. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackingGetQueueSize(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackingClearQueue </p> </td> 
   <td colname="col2"> <p>Removes all stored tracking calls from the offline queue. Warning: use caution when clearing the queue manually as it cannot be reversed. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackingClearQueue(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;});&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>keepLifecycleSessionAlive </p> </td> 
   <td colname="col2"> <p>Indicates to the SDK that your next resume from background should not start a new session, regardless of the value of lifecycle session timeout in your config file. </p> 
    <!--iOS Only--> <p>Important:  this method is intended to be used for apps that register for notifications while in background and should only be called from your code that runs while your app is in the background. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.keepLifecycleSessionAlive(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>collectLifecycleData </p> </td> 
   <td colname="col2"> <p>Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. For more information, see <a href="../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics </a>. </p> 
    <!--iOS Only--> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.collectLifecycleData(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## PII Methods {#section_DB27270D2CEB4D369E0090FD9D1A7F81}

<table id="table_FA9F226DBE5B4854A39AE5B1694C10EC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Method </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>collectPII </p> </td> 
   <td colname="col2"> <p> Submits a PII collection request. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.collectPII(piiData,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.collectPII({'k1':'v1','k2':'v2','k3':'v3'},&nbsp;function&nbsp;(value)&nbsp;{&nbsp;alert('success');&nbsp;},function&nbsp;(value)&nbsp;{&nbsp;alert('fail');&nbsp;});
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Tracking Methods {#section_7946BB753A4446FE8A3ED728AEF97D04}

<table id="table_44EBEADED1664618924DFCB478BE4C83"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Method </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> trackAdobeDeepLink </p> </td> 
   <td colname="col2"> <p> Tracks an Adobe Deep Link click-through. </p> <p> <p>Tip:  If the Lifecycle call is a launch event, the Adobe Link data will be appended, otherwise an extra call will be sent. </p> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackAdobeDeepLink(deeplinkURL,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackAdobeDeepLink('xyz-deeplink-url',&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackPushMessageClickthrough </p> </td> 
   <td colname="col2"> <p> Tracks a push message click-through. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackPushMessageClickthrough(userInfo,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackPushMessageClickthrough({'k1':'v1','k2':'v2','k3':'v3'},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackLocalNotificationClickThrough </p> </td> 
   <td colname="col2"> <p> Tracks a local notification message click-through. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackLocalNotificationClickThrough(userInfo,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackLocalNotificationClickThrough({'k1':'v1','k2':'v2','k3':'v3'},&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackState </p> </td> 
   <td colname="col2"> <p>Tracks an app state with optional context data. States are the views that are available in your app, such as <span class="codeph"> home dashboard </span>, <span class="codeph"> app settings </span>, <span class="codeph"> cart, </span> and so on. These states are similar to pages on a website, and <span class="codeph"> trackState </span> calls increment page views. </p> <p>cData: JSON object with key-value pairs to send in context data. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackState(string&amp;nbsp;stateName[,JSON&amp;nbsp;cData]); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackState("login&amp;nbsp;page"); 
    </codeblock> 
    <codeblock class="syntax javascript">
      ADB.trackState("login&amp;nbsp;page",&amp;nbsp;{"user":"john","remember":"true"}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackAction </p> </td> 
   <td colname="col2"> <p>Tracks an action in your app. Actions are the things that happen in your app that you want to measure, include <span class="codeph"> logins </span>, <span class="codeph"> banner taps </span>, <span class="codeph"> feed subscriptions </span> and other metrics. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackAction(string&amp;nbsp;action[,JSON&amp;nbsp;cData]); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackAction("login"); 
    </codeblock> 
    <codeblock class="syntax javascript">
      ADB.trackAction("login",&amp;nbsp;{"user":"john","remember":"true"}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackActionFromBackground </p> </td> 
   <td colname="col2"> <p> Tracks an action that occurred in the background. This suppresses lifecycle events from firing in certain scenarios. </p> 
    <!--iOS Only--> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackActionFromBackground(string&amp;nbsp;action[,JSON&amp;nbsp;cData]); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.trackActionFromBackground("login"); 
    </codeblock> 
    <codeblock class="syntax javascript">
      ADB.trackActionFromBackground("login",&amp;nbsp;{"user":"john","remember":"true"}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackLocation </p> </td> 
   <td colname="col2"> <p>Sends the current x y coordinates. Also uses points of interest defined in the <span class="codeph"> ADBMobileConfig.json </span> file to determine if the location provided as a parameter is within any of your POI. If the current coordinates are within a defined POI, a context data variable is populated and sent with the <span class="codeph"> trackLocation </span> call. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackLocation(x,&amp;nbsp;y[,JSON&amp;nbsp;cData]); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackLocation('40.431596',&amp;nbsp;'-111.893713'); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackLifetime​ValueIncrease </p> </td> 
   <td colname="col2"> <p> Adds <span class="codeph"> amount </span> to the user's lifetime value. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackLifetimeValueIncrease(amount[,JSON&amp;nbsp;cData]); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackLifetimeValueIncrease('10.01'); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackTimed​ActionStart </p> </td> 
   <td colname="col2"> <p>Start a timed action with name <span class="codeph"> action </span>. </p> <p> If you call this method for an action that has already started, the previous timed action is overwritten. </p> <p>Tip:  This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackTimedActionStart(action[,JSON&amp;nbsp;cData]); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackTimedActionStart("cartToCheckout"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackTimed​ActionUpdate </p> </td> 
   <td colname="col2"> <p> Pass in <span class="codeph"> cData </span> to update the context data associated with the given <span class="codeph"> action </span>. </p> <p>The <span class="codeph"> cData </span> passed in is appended to the existing data for the given action, and overwrites the data if the same key is already defined for <span class="codeph"> action </span>. </p> <p>Tip:  This call does not send a hit. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackTimedActionUpdate(String&amp;nbsp;action[,JSON&amp;nbsp;cData]); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackTimedActionUpdate("cartToCheckout",{'SampleContextDataKey3':'SampleContextDataVal3','SampleContextDataKey4':'SampleContextDataVal4'}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackTimed​ActionEnd </p> </td> 
   <td colname="col2"> <p> End a timed action. </p> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackTimedActionEnd("cartToCheckout"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>trackingTimedActionExists </p> </td> 
   <td colname="col2"> <p> Returns whether or not a timed action is in progress. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.trackingTimedActionExists(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;myTempVal&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Target Methods {#section_C45D2FE54AE04EB5BD24D3508F8A3212}

<table id="table_258F21CC9F1A459597E95D7BFEEE2ACE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Method </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>targetLoadRequest </p> </td> 
   <td colname="col2"> <p>Sends request to your configured <span class="keyword"> Target </span> server and returns the string value of the offer. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadRequest(success,&amp;nbsp;fail,&amp;nbsp;name,&amp;nbsp;defaultContent,&amp;nbsp;parameters); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadRequest(function&nbsp;(value){&nbsp;myTempVal&nbsp;=&nbsp;value;&nbsp;},&nbsp;function&nbsp;()&nbsp;{&nbsp;myTempVal&nbsp;=&nbsp;null;&nbsp;},&nbsp;'bannerOffer',&nbsp;'none',&nbsp;{'hp':'hp_val_new','hp.company':'adobe',&nbsp;'hp.val2':'hp_val2'}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetLoadOrderConfirmRequest </p> </td> 
   <td colname="col2"> <p>Sends a request to your configured <span class="keyword"> Target </span> server. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadOrderConfirmRequest(success,&amp;nbsp;fail,&amp;nbsp;name,&amp;nbsp;orderId,&amp;nbsp;orderTotal,&amp;nbsp;productPurchaseId,&amp;nbsp;parameters); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadRequest(function&nbsp;(value)&nbsp;{&nbsp;myTempVal&nbsp;=&nbsp;value;&nbsp;},&nbsp;function&nbsp;(){&nbsp;myTempVal&nbsp;=&nbsp;null;&nbsp;},&nbsp;'name',&nbsp;'orderId',&nbsp;'total',&nbsp;'purchaseId',{'hp':'hp_val_new','hp.company':'adobe',&nbsp;'hp.val2':'hp_val2'}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetClearCookies </p> </td> 
   <td colname="col2"> <p>Clears the <span class="keyword"> Target </span> cookies from shared cookie storage. </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetClearCookies(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetLoadRequestWithNameWithLocationParameters </p> </td> 
   <td colname="col2"> <p> Processes a <span class="keyword"> Target </span> service request. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadRequestWithNameWithLocationParameters(success,&nbsp;fail,&nbsp;name,&nbsp;defaultContent,&nbsp;profileParameters,&nbsp;orderParameters,&nbsp;mboxParameters,&nbsp;requestLocationParameters); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadRequestWithNameWithLocationParameters&amp;nbsp;(function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;},&amp;nbsp;'bannerOffer',&amp;nbsp;'none',&amp;nbsp;{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'},&amp;nbsp;{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'},{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'},{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetLoadRequestWithName </p> </td> 
   <td colname="col2"> <p> Processes a <span class="keyword"> Target </span> service request. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadRequestWithRequestLocationParams(success,&nbsp;fail,&nbsp;name,&nbsp;defaultContent,&nbsp;profileParameters,&nbsp;orderParameters,&nbsp;mboxParameters,&nbsp;requestLocationParameters); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadRequestWithRequestLocationParams(function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;},&amp;nbsp;'bannerOffer',&amp;nbsp;'none',&amp;nbsp;{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'},&amp;nbsp;{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'},{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetSessionID </p> </td> 
   <td colname="col2"> <p> Gets the value of the <span class="codeph"> SessionID </span> cookie returned for this visitor by the <span class="keyword"> Target </span> server. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetSessionID&amp;nbsp;(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetSessionID(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert(value);&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetPcID </p> </td> 
   <td colname="col2"> <p> Gets the value of the <span class="codeph"> PcID </span> cookie returned for this visitor by the <span class="keyword"> Target </span> server. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetPcID&amp;nbsp;(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetPcID(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert(value);&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetSetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Sets the custom visitor ID for <span class="keyword"> Target </span>. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetSetThirdPartyID(thirdPartyID,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetSetThirdPartyID('test-third-party-id',&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> targetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Gets the custom visitor ID for <span class="keyword"> Target </span>. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetThirdPartyID(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetThirdPartyID(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert(value);&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Acquisition Methods {#section_EDEA25C4B2884487827069E9257A0BA6}

<table id="table_0A4C95821E5040B3B6AF98CD07027111"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Method </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>acquisitionCampaignStartForApp </p> </td> 
   <td colname="col2"> <p>Allows developers to start an app acquisition campaign as if the user had clicked a link. This is helpful for creating manual acquisition links and handling the app store redirect yourself (such as with an <span class="codeph"> SKStoreView </span>). </p> <p> <b>Syntax:</b> </p> 
    <codeblock>
      ADB.acquisitionCampaignStartForApp(appId,&amp;nbsp;data,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p> <b>Example: </b> </p> 
    <codeblock>
      ADB.acquisitionCampaignStartForApp('0652024f-adcd-49f9-9bd7-2552a4564d2f',&amp;nbsp;{'extraDataKey':'extraDataValue'},&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Advertising Identifier {#section_194607D101B047A19C51B19E176E1500}

In the `AppDelegate` generated by Cordova, call `[ADBMobile setAdvertisingIdentifier:]` in the `application:didFinishLaunchingWithOptions:` delegate method.

See [Configuration Methods](../configuration/sdk-methods.md#concept_41E8501BF7514CC3A68679D7F2A49EEA).

## Audience Manager Methods {#section_1FD12B29A0AF41D3BEACBB3D624EA0E4}

<table id="table_529CF2B892EB483084DDD46B11AC82D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Method </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>audienceGetVisitorProfile </p> </td> 
   <td colname="col2"> <p>Gets the visitor’s profile. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceGetVisitorProfile(); 
    </codeblock> <p> </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceGetVisitorProfile(function(value)&amp;nbsp;{&amp;nbsp;profile&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function()&amp;nbsp;{&amp;nbsp;profile&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>audienceGetDpuuid </p> </td> 
   <td colname="col2"> <p>Returns the DPUUID. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceGetDpuuid(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceGetDpuuid(function(value)&amp;nbsp;{&amp;nbsp;dpuuid&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function()&amp;nbsp;{&amp;nbsp;dpuuid&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>audienceGetDpid </p> </td> 
   <td colname="col2"> <p>Returns the DPID. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceGetDpid(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceGetDpid(function(value)&amp;nbsp;{&amp;nbsp;dpid&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function()&amp;nbsp;{&amp;nbsp;dpid&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>audienceSetDpidAndDpuuid </p> </td> 
   <td colname="col2"> <p>Sets the DPID and DPUUID. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceSetDpidAndDpuuid(dpid,&amp;nbsp;dpuuid,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceSetDpidAndDpuuid(‘dpid’,&amp;nbsp;‘dpuuid’,&amp;nbsp;function()&amp;nbsp;{…},&amp;nbsp;function()&amp;nbsp;{…}); 
    </codeblock> 
    <codeblock class="syntax java">
      ADB.audienceSetDpidAndDpuuid(‘dpid’,&amp;nbsp;‘dpuuid’); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>audienceSignalWithData </p> </td> 
   <td colname="col2"> <p>Processes an Audience Manager service request. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceSignalWithData(success,&amp;nbsp;fail,&amp;nbsp;data); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceSignalWithData(function()&amp;nbsp;{},&amp;nbsp;function()&amp;nbsp;{},&amp;nbsp;{‘key1’:&amp;nbsp;’value1’,&amp;nbsp;‘key2’:&amp;nbsp;‘value2’}); 
    </codeblock> 
    <codeblock class="syntax java">
      ADB.audienceSignalWithData({‘key1’:&amp;nbsp;’value1’,&amp;nbsp;‘key2’:&amp;nbsp;‘value2’}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>audienceReset </p> </td> 
   <td colname="col2"> <p>Resets audience manager UUID and purges current visitor profile. </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.audienceReset(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## ID Service Methods {#section_840B4FAEA55B466F9754148ABA15EBDA}

<table id="table_AB60E0C194004E9A930B0FFFAA55A356"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Method </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>visitorGetMarketingCloudId </p> </td> 
   <td colname="col2"> <p>Returns the Experience Cloud ID from the ID service. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorGetMarketingCloudId(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorGetMarketingCloudId(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorSyncIdentifiers </p> </td> 
   <td colname="col2"> <p>Synchronizes the provided identifiers with the ID service. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifiers(identifiers,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifiers({‘key_id_1’:’value_id_1’},&amp;nbsp;function()&amp;nbsp;{…},&amp;nbsp;function()&amp;nbsp;{…})); 
    </codeblock> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifiers({‘key_id_1’:&amp;nbsp;‘value_id_1’});&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> visitorSyncIdentifiersWithAuthenticationState </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifiers to the visitor ID service. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifiersWithAuthenticationState(identifiers,&amp;nbsp;authenticationState,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifiersWithAuthenticationState({'k1':'v1','k2':'v2','k3':'v3'},&amp;nbsp;ADB.mobileVisitorAuthenticationStateAuthenticated,&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> visitorSyncIdentifierWithType </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifier to the visitor ID service. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifierWithType(identifierType,&amp;nbsp;identifier,&amp;nbsp;authenticationState,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifierWithType('test-identifier-type',&amp;nbsp;'test-identifier',&amp;nbsp;ADB.mobileVisitorAuthenticationStateAuthenticated,&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> visitorAppendToURL </p> </td> 
   <td colname="col2"> <p> Appends visitor identifiers to the given URL. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorAppendToURL(urlToAppend,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorAppendToURL('test_visitor_url',&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert(value);&amp;nbsp;},''); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> visitorGetIDs </p> </td> 
   <td colname="col2"> <p> Returns all <span class="codeph"> visitorIDs </span> that have been synced. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorGetIDs&amp;nbsp;(success,&amp;nbsp;fail) 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorGetIDs(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert(value);&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>
