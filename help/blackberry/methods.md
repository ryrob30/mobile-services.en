---
description: Classes and methods provided by the BlackBerry library.
seo-description: Classes and methods provided by the BlackBerry library.
seo-title: Adobe Mobile class and method reference
title: Adobe Mobile class and method reference
uuid: 1e42d759-be43-4bb3-ac1a-c7d64133d61c
index: y
internal: n
snippet: y
---

# Adobe Mobile class and method reference{#adobe-mobile-class-and-method-reference}

Classes and methods provided by the BlackBerry library.

 The SDK currently has support for Adobe Analytics, and methods are in separate classes based on the solution. The list of solutions and each class is as follows: 

|  Solution  | Class  |
|---|---|
|  Analytics  | Analytics  |

## SDK Settings {#section_C1EB977043C04D2B93E5A63DB72828B6}

<table id="table_74D286D1763D4C9F996C2E95A1FEFB39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> getPrivacyStatus </td> 
   <td colname="col2"> <p>Returns the enum representation of the privacy status for current user. </p> 
    <ul id="ul_9B1847F75F49466796B5929C485DA9DD"> 
     <li id="li_738965BC048044B5A6ACCE02FC84E74E"> <span class="codeph"> ADBMobilePrivacyStatusOptIn </span> - hits are sent immediately. </li> 
     <li id="li_9BB3A31DC62B4EE6AEC364145463E09B"> <span class="codeph"> ADBMobilePrivacyStatusOptOut </span> - hits are discarded. </li> 
     <li id="li_AF7571F4B2614B8EAAC43F17216626CF"> <span class="codeph"> ADBMobilePrivacyStatusUnknown </span> - If your report suite is timestamp-enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If your report suite is not timestamp-enabled, hits are discarded until the privacy status changes to opt in. </li> 
    </ul> <p>Default: The default value is set in <span class="codeph"> <a href="methods.md#section_5AD4EDF87E304980B4AC4A5657FDA8B9" format="dita" scope="local"> ADBMobileConfig.json </a> </span> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;ADBMobilePrivacyStatus&amp;nbsp;getPrivacyStatus(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      &amp;nbsp;ADBMobilePrivacyStatus&amp;nbsp;privacyStatus&amp;nbsp;=&amp;nbsp;ADBMobile::getPrivacyStatus(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setPrivacyStatus </td> 
   <td colname="col2"> <p>Sets the privacy status for the current user to <span class="codeph"> status </span>. Set to one of the following values: </p> 
    <ul id="ul_81E2AB9E329F421C8CBA3339D8BAD9F9"> 
     <li id="li_906A173525AE43A1887B745AB2ADA5FB"> <span class="codeph"> ADBMobilePrivacyStatusOptIn </span> - hits are sent immediately. </li> 
     <li id="li_76C56A6F19434A2E8A3A211C556F26EE"> <span class="codeph"> ADBMobilePrivacyStatusOptOut </span> - hits are discarded. </li> 
     <li id="li_14E722A07AF442B5B5F9492B3B832A17"> <span class="codeph"> ADBMobilePrivacyStatusUnknown </span> - If your report suite is timestamp-enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If your report suite is not timestamp-enabled, hits are discarded until the privacy status changes to opt in. </li> 
    </ul> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;void&amp;nbsp;setPrivacyStatus(ADBMobilePrivacyStatus&amp;nbsp;status); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      &amp;nbsp;ADBMobile::setPrivacyStatus(ADBMobilePrivacyStatusOptIn); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getUserIdentifier </td> 
   <td colname="col2"> <p>Returns the user identifier if a custom identifier has been set. Returns null if a custom identifier is not set. </p> <p>Default: <span class="codeph"> null </span> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;QString&amp;nbsp;getUserIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      &amp;nbsp;QString&amp;nbsp;userId&amp;nbsp;=&amp;nbsp;ADBMobile::getUserIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setUserIdentifier </td> 
   <td colname="col2"> <p>Sets the user identifier to <span class="codeph"> identifier </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;void&amp;nbsp;setUserIdentifier(QString&amp;nbsp;identifier); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMobile::setUserIdentifier("billybob"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> getDebugLogging </td> 
   <td colname="col2"> <p>Returns the current debug logging preference. </p> <p>Default: false </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;bool&amp;nbsp;getDebugLogging(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      &amp;nbsp;bool&amp;nbsp;debugging&amp;nbsp;=&amp;nbsp;ADBMobile::getDebugLogging(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setDebugLogging </td> 
   <td colname="col2"> <p>Sets the debug logging preference to <span class="codeph"> debugLogging </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;void&amp;nbsp;setDebugLogging(bool&amp;nbsp;debugLogging); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMobile::setDebugLogging(true); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> collectLifecycleData </td> 
   <td colname="col2"> <p>Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. See <a href="metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;void&amp;nbsp;collectLifecycleData(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ApplicationUI::ApplicationUI(bb::cascades::Application&nbsp;*app):&nbsp;QObject(app)&nbsp;{ 
     
//... 
     
ADBMobile::collectLifecycleData(); 
     
}

    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Analytics Methods {#section_91F4AD0A045D4E4E8F9A93450503E49E}

Each of these methods is used to send data into your Adobe Analytics report suite. 

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
   <td colname="col2"> <p>Tracks an app state with optional context data. States are the views that are available in your app, such as "home dashboard", "app settings", "cart", and so on. These states are similar to pages on a website, and <span class="codeph"> trackState </span> calls increment page views. </p> <p>Note:  This is the only tracking call that increments page views. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;void&amp;nbsp;trackState(QString&amp;nbsp;state,&amp;nbsp;QHash&lt;QString,&amp;nbsp;QString&gt;&amp;nbsp;contextData&amp;nbsp;=&amp;nbsp;QHash&lt;QString,&amp;nbsp;QString&gt;()); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      &amp;nbsp;ADBMobile::trackState("loginScreen",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackAction </td> 
   <td colname="col2"> <p>Tracks an action in your app. Actions are the things that happen in your app that you want to measure, such as "logons", "banner taps", "feed subscriptions", and other metrics. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;void&amp;nbsp;trackAction(QString&amp;nbsp;action,&amp;nbsp;QHash&lt;QString,&amp;nbsp;QString&gt;&amp;nbsp;contextData&amp;nbsp;=&amp;nbsp;QHash&lt;QString,&amp;nbsp;QString&gt;()); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMobile::trackAction("heroBannerTouched",&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLocation </td> 
   <td colname="col2"> <p>Sends the current x y coordinates. Replace event with the event that is received from the subscriber to BPS. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax cpp">
      static&amp;nbsp;void&amp;nbsp;trackLocation(bps_event_t&amp;nbsp;*geoEvent,&amp;nbsp;QHash&lt;QString,&amp;nbsp;QString&gt;&amp;nbsp;contextData&amp;nbsp;=&amp;nbsp;QHash&lt;QString,&amp;nbsp;QString&gt;()); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax cpp">
      ADBMobile::trackLocation(event,&amp;nbsp;null); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## ADBMobileConfig.json Config File Reference {#section_5AD4EDF87E304980B4AC4A5657FDA8B9}

The [!DNL ADBMobileConfig.json] must be placed in the [!DNL assets] folder. 

<table id="table_4068E4D18FA043DA902A2B67731348F2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> rsids </td> 
   <td colname="col2"> <p>(Required) One or more report suites to receive Analytics data. Multiple report suite IDs should be comma-separated with no space between. </p> 
    <codeblock>
      "rsids"&amp;nbsp;:&amp;nbsp;"rsid" 
    </codeblock> 
    <codeblock>
      "rsids"&amp;nbsp;:&amp;nbsp;"rsid1,rsid2" 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> server </td> 
   <td colname="col2"> <p>(Required). Analytics server. </p> <p> This variable should be populated with the server domain, without an "http://" or https://" protocol prefix. The protocol prefix is handled automatically by the library based on the <span class="codeph"> ssl </span> variable. </p> <p> If <span class="codeph"> ssl </span> is <span class="codeph"> true </span>, a secure connection is made to this server. If <span class="codeph"> ssl </span> is <span class="codeph"> false </span>, a non-secure connection is made to this server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> charset </td> 
   <td colname="col2"> Defines the character set you are using for the data sent to Analytics. The charset is used to convert incoming data into UTF-8 for storage and reporting. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ssl </td> 
   <td colname="col2"> <p>Default: false </p> <p>Enables (true) or disables (false) sending measurement data via SSL (HTTPS). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> offlineEnabled </td> 
   <td colname="col2"> <p>Default: false </p> <p>When enabled (true), hits are queued while the device is offline and sent later when the device is online. Your report suite must be timestamp-enabled to use offline tracking. </p> <p>Important:  If timestamps are enabled on your report suite, your <span class="codeph"> offlineEnabled </span> configuration property <i>must</i> be true. if your report suite is not timestamp enabled, your <span class="codeph"> offlineEnabled </span> configuration property <i>must</i> be false. If this is not configured correctly, data will be lost. If you are not sure if a report suite is timestamp enabled, contact Customer Care. </p> <p>If you are currently reporting AppMeasurement data to a report suite that also collects data from JavaScript, you might need to set up a separate report suite for mobile data, or include a custom timestamp on all JavaScript hits using the <span class="codeph"> s.timestamp </span> variable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> lifecycleTimeout </td> 
   <td colname="col2"> <p>Default: 300 seconds </p> <p>Specifies the length of time, in seconds, that must elapse between app launches before the launch is considered a new session. This timeout also applies when your application is sent to the background and reactivated. The time that your app spends in the background is not included in the session length. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> batchLimit </td> 
   <td colname="col2"> <p>Default: 0 (No limit) </p>Maximum number of offline hits stored in the queue. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> privacyDefault </td> 
   <td colname="col2"> <p>Default: <span class="codeph"> optedin </span> </p> 
    <ul id="ul_B7A92BD8C9BA4EFEA5CCD451A76042BD"> 
     <li id="li_B6F78E8FE4DD4872B3DC2FBA656DBCDE"> <span class="codeph"> optedin </span> - hits are sent immediately. </li> 
     <li id="li_EF1EF12AF30C4E8D86F0F62E37F1B90E"> <span class="codeph"> optedout </span> - hits are discarded. </li> 
     <li id="li_BBF64ECCC33B40519F9C4221077C12A1"> <span class="codeph"> optunknown </span> - If your report suite is timestamp-enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If your report suite is not timestamp-enabled, hits are discarded until the privacy status changes to opt in. </li> 
    </ul> <p>This sets the initial value only. If this value is ever set or changed in code, then the new value is used going forward until it is changed, or the app is uninstalled and then reinstalled. </p> </td> 
  </tr> 
 </tbody> 
</table>

The following is an example of an `ADBMobileConfig.json` file:

```js
{ 
    "version" : "1.0", 
    "analytics" : { 
        "rsids" : "coolApp", 
        "server" : "my.CoolApp.com", 
        "charset" : "UTF-8", 
        "ssl" : false, 
        "offlineEnabled" : true, 
        "lifecycleTimeout" : 5, 
        "privacyDefault" : "optedin", 
    } 
}
```

