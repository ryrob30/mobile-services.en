---
description: Classes and methods provided by the Universal Windows Platform library.
seo-description: Classes and methods provided by the Universal Windows Platform library.
seo-title: SDK methods
solution: Marketing Cloud,Analytics
title: SDK methods
topic: Developer and implementation
uuid: e3aa41d6-7bc0-4208-a662-12907c209a77
---

# SDK methods{#sdk-methods}

Classes and methods provided by the Universal Windows Platform library.

>[!NOTE]
>
>When you consume winmd methods from winJS (JavaScript), all methods automatically have their first letter lowercased.

<table id="table_74D286D1763D4C9F996C2E95A1FEFB39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> GetVersion <p>winJS: getVersion </p> </td> 
   <td colname="col2"> <p> Returns the current version of the Adobe Mobile library. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Platform::String&amp;nbsp;^GetVersion(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;var&nbsp;libVersion&nbsp;=&nbsp;ADB.Config.getVersion(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetPrivacyStatusAsync <p>winJS: getPrivacyStatusAsync </p> </td> 
   <td colname="col2"> <p>Returns the enum representation of the privacy status for current user. </p> 
    <ul id="ul_395A791E516549A4A8A54339B05DA020"> 
     <li id="li_31C07091DDE0493D9EF3F3E5E3D7F791"> <span class="codeph"> ADBMobilePrivacyStatusOptIn </span> - hits are sent immediately. </li> 
     <li id="li_DB17FA95B9C44AADA0C2DCD965ADCD56"> <span class="codeph"> ADBMobilePrivacyStatusOptOut </span> - hits are discarded. </li> 
     <li id="li_204BBF14BB834C95B6B1B5547B5DDB7F"> <span class="codeph"> ADBMobilePrivacyStatusUnknown </span> - If your report suite is timestamp-enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If your report suite is not timestamp-enabled, hits are discarded until the privacy status changes to opt in. </li> 
    </ul> <p>Default: The default value is set in <span class="codeph"> <a href="../c-configuration/methods.md#section_5AD4EDF87E304980B4AC4A5657FDA8B9" format="dita" scope="local"> ADBMobileConfig.json </a> </span> </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Windows::Foundation::IAsyncOperation&lt;ADBMobilePrivacyStatus&gt;&amp;nbsp;^getPrivacyStatusAsync(); 
    </codeblock> 
    <codeblock class="syntax csharp">
      public&nbsp;enum&nbsp;class&nbsp;ADBMobilePrivacyStatus&nbsp;:&nbsp;int&nbsp;{&nbsp;ADBMobilePrivacyStatusOptIn&nbsp;=&nbsp;1,&nbsp;ADBMobilePrivacyStatusOptOut&nbsp;=&nbsp;2,&nbsp;ADBMobilePrivacyStatusUnknown&nbsp;=&nbsp;3}; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;var&nbsp;status;ADB.Config.getPrivacyStatusAsync.then(function(privacyStatus)&nbsp;{status&nbsp;=&nbsp;privacyStatus;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SetPrivacyStatus <p>winJS: setPrivacyStatus </p> </td> 
   <td colname="col2"> <p>Sets the privacy status for the current user to <span class="codeph"> status </span>. Set to one of the following values: </p> 
    <ul id="ul_55894773EF51490AB162F0227AE9EEDD"> 
     <li id="li_257F818CBB144C34843840E3FED3B881"> <span class="codeph"> ADBMobilePrivacyStatusOptIn </span> - hits are sent immediately. </li> 
     <li id="li_199FDE7713A84A0FA810D5130F8002B8"> <span class="codeph"> ADBMobilePrivacyStatusOptOut </span> - hits are discarded. </li> 
     <li id="li_DA25DEED309040D39A8D6E9A6D6BCDAC"> <span class="codeph"> ADBMobilePrivacyStatusUnknown </span> - If your report suite is timestamp-enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If your report suite is not timestamp-enabled, hits are discarded until the privacy status changes to opt in. </li> 
    </ul> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;SetPrivacyStatus(ADBMobilePrivacyStatus&amp;nbsp;status); 
    </codeblock> 
    <codeblock class="syntax csharp">
      public&nbsp;enum&nbsp;class&nbsp;ADBMobilePrivacyStatus&nbsp;:&nbsp;int&nbsp;{&nbsp;ADBMobilePrivacyStatusOptIn&nbsp;=&nbsp;1,&nbsp;ADBMobilePrivacyStatusOptOut&nbsp;=&nbsp;2,&nbsp;ADBMobilePrivacyStatusUnknown&nbsp;=&nbsp;3}; 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;ADB.Config.setPrivacyStatus(ADB.ADBMobilePrivacyStatus.adbmobilePrivacyStatusOptIn); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetLifetimeValue <p>winJS: getLifetimeValue </p> </td> 
   <td colname="col2"> <p>Returns the lifetime value of the current user. </p> <p>Default: 0 </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;float&amp;nbsp;GetLifetimeValue(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;var&nbsp;ltv&nbsp;=&nbsp;ADB.Config.getLifetimeValue(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetUserIdentifier <p>winJS: getUserIdentifier </p> </td> 
   <td colname="col2"> <p>Returns the custom user identifier if a custom identifier has been set. Returns null if a custom identifier is not set. </p> <p>Default: <span class="codeph"> null </span> </p> <p>Note:  If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous ID service (either custom or automatically generated) is retrieved and stored as the custom user identifier. This preserves visitor data between upgrades of the SDK. For new installations on the 4.x SDK, user identifier is <span class="codeph"> null </span> until set. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Platform::String&amp;nbsp;^GetUserIdentifier(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax csharp">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;var&nbsp;userId&nbsp;=&nbsp;ADB.Config.getUserIdentifier(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SetUserIdentifier <p>winJS: setUserIdentifier </p> </td> 
   <td colname="col2"> <p>Sets the user identifier to <span class="codeph"> identifier </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;SetUserIdentifier(Platform::String&amp;nbsp;^userIdentifier); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;ADB.Config.setUserIdentifier("someUserId"); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetDebugLogging <p>winJS: getDebugLogging </p> </td> 
   <td colname="col2"> <p>Returns the current debug logging preference. </p> <p>Default: false </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;bool&amp;nbsp;GetDebugLogging(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;var&nbsp;logging&nbsp;=&nbsp;ADB.Config.getDebugLogging(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SetDebugLogging <p>winJS: setDebugLogging </p> </td> 
   <td colname="col2"> <p>Sets the debug logging preference to <span class="codeph"> debugLogging </span>. Debug logging works only when using the debug version of the library, the release version ignores this setting. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;SetDebugLogging(bool&amp;nbsp;debugLogging); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;ADB.Config.setDebugLogging(true); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CollectLifecycleData <p>winJS: collectLifecycleData </p> </td> 
   <td colname="col2"> <p>Indicates to the SDK that lifecycle data should be collected for use across all solutions in the SDK. See <a href="../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;CollectLifecycleData(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;ADB.Config.collectLifecycleData(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PauseCollecting​LifecycleData <p>winJS: pauseCollecting​LifecycleData </p> </td> 
   <td colname="col2"> <p>Indicates to the SDK that your app is paused, so that lifecycle metrics are calculated correctly. For example, on pause collects a timestamp to determine previous session length. This also sets a flag so that lifecyle correctly knows that the app did not crash. See <a href="../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics </a>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;PauseCollectingLifecycleData(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile;ADB.Config.pauseCollectingLifecycleData(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>
