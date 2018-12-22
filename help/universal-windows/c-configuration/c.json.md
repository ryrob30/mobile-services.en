---
description: Information to help you use the ADBMobile JSON Config file.
seo-description: Information to help you use the ADBMobile JSON Config file.
seo-title: ADBMobileConfig.json config
solution: Marketing Cloud,Analytics
title: ADBMobileConfig.json config
topic: Developer and implementation
uuid: cbcb54a3-4b8f-4651-8ce9-2731ac988545
---

# ADBMobileConfig.json config{#adbmobileconfig-json-config}

Information to help you use the ADBMobile JSON Config file.

The SDK currently has support for multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], and [!DNL Audience Manager]. Methods are prefixed according to the solution. Configuration methods are prefixed with "Config." 

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
   <td colname="col2"> <p>(Required by Analytics) One or more report suites to receive Analytics data. Multiple report suite IDs should be comma-separated with no space between. </p> 
    <codeblock class="syntax javascript">
      "rsids"&amp;nbsp;:&amp;nbsp;"rsid" 
    </codeblock> 
    <codeblock class="syntax javascript">
      "rsids"&amp;nbsp;:&amp;nbsp;"rsid1,rsid2" 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> server </td> 
   <td colname="col2"> <p>(Required by Analytics and Audience Management). Analytics or Audience Management server, based on the parent node. </p> <p> This variable should be populated with the server domain, without an "https://" or https://" protocol prefix. The protocol prefix is handled automatically by the library based on the <span class="codeph"> ssl </span> variable. </p> <p> If <span class="codeph"> ssl </span> is <span class="codeph"> true </span>, a secure connection is made to this server. If <span class="codeph"> ssl </span> is <span class="codeph"> false </span>, a non-secure connection is made to this server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> charset </td> 
   <td colname="col2"> Defines the character set you are using for the data sent to Analytics. The charset is used to convert incoming data into UTF-8 for storage and reporting. See <a href="https://microsite.omniture.com/t2/help/en_US/whitepapers/multibyte/?f=multibyte_charset.html" format="http" scope="external"> Using the charSet Property </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ssl </td> 
   <td colname="col2"> <p>Default: false </p> <p>Enables (true) or disables (false) sending measurement data via SSL (HTTPS). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> offlineEnabled </td> 
   <td colname="col2"> <p>Default: false </p> <p>When enabled (true), hits are queued while the device is offline and sent later when the device is online. Your report suite must be timestamp-enabled to use offline tracking. </p> <p>Important:  If time stamps are enabled on your report suite, your <span class="codeph"> offlineEnabled </span> configuration property <i>must</i> be true. if your report suite is not timestamp enabled, your <span class="codeph"> offlineEnabled </span> configuration property <i>must</i> be false. If this is not configured correctly, data will be lost. If you are not sure if a report suite is timestamp enabled, contact Customer Care. </p> <p>If you are currently reporting AppMeasurement data to a report suite that also collects data from JavaScript, you might need to set up a separate report suite for mobile data, or include a custom timestamp on all JavaScript hits using the <span class="codeph"> s.timestamp </span> variable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> lifecycleTimeout </td> 
   <td colname="col2"> <p>Default: 300 seconds </p> <p>Specifies the length of time, in seconds, that must elapse between app launches before the launch is considered a new session. This timeout also applies when your application is sent to the background and reactivated. The time that your app spends in the background is not included in the session length. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> batchLimit </td> 
   <td colname="col2"> <p>Default: 0 (No batching) </p>Send hits in batches. For example, if set to 50, hits are queued until 50 are stored, then all queued hits are sent. Requires <span class="codeph"> offlineEnabled=true </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> privacyDefault </td> 
   <td colname="col2"> <p>Default: <span class="codeph"> optedin </span> </p> 
    <ul id="ul_B7A92BD8C9BA4EFEA5CCD451A76042BD"> 
     <li id="li_B6F78E8FE4DD4872B3DC2FBA656DBCDE"> <span class="codeph"> optedin </span> - hits are sent immediately. </li> 
     <li id="li_EF1EF12AF30C4E8D86F0F62E37F1B90E"> <span class="codeph"> optedout </span> - hits are discarded. </li> 
     <li id="li_BBF64ECCC33B40519F9C4221077C12A1"> <span class="codeph"> optunknown </span> - If your report suite is timestamp-enabled, hits are saved until the privacy status changes to opt-in (then hits are sent) or opt-out (then hits are discarded). If your report suite is not timestamp-enabled, hits are discarded until the privacy status changes to opt in. </li> 
    </ul> <p>Note:  This sets the default value only. If this value is ever set or changed in code, then the value set by the code is saved in local storage and is used going forward until it is changed, or the app is uninstalled and then reinstalled. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> poi </td> 
   <td colname="col2"> <p>Each POI array holds the POI name, latitude, longitude, and radius (in meters) for the area of the point. The POI name can be any string. </p> <p>When a <span class="codeph"> trackLocation </span> call is sent, if the current coordinates are within a defined POI, a context data variable is populated and sent with the <span class="codeph"> trackLocation </span> call. </p> 
    <codeblock class="syntax javascript">
      "poi"&nbsp;:&nbsp;[ 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;["san&nbsp;francisco",37.757144,-122.44812,7000], 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;["santa&nbsp;cruz",36.972935,-122.01725,600] 
     
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;] 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> clientCode </td> 
   <td colname="col2"> (Required by Target) Your assigned client code. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> timeout </td> 
   <td colname="col2"> Determines how long target waits for a response. </td> 
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
        "poi" : [ 
                    ["san francisco",37.757144,-122.44812,7000], 
                    ["santa cruz",36.972935,-122.01725,600] 
                ] 
    }, 
 "target" : { 
  "clientCode" : "myTargetClientCode", 
  "timeout" : 1 
 }, 
 "audienceManager" : { 
  "server" : "myServer.demdex.com" 
 } 
}
```

