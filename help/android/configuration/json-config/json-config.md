---
description: This information helps you use the ADBMobile.json config file.
seo-description: This information helps you use the ADBMobile.json config file.
seo-title: ADBMobile JSON Config
solution: Marketing Cloud,Analytics
title: ADBMobile JSON Config
topic: Developer and implementation
uuid: 1decf605-7bc3-4e73-ad52-1ecd5821599e
---

# ADBMobile JSON Config {#adbmobile-json-config}

This information helps you use the ADBMobile.json config file.

This section contains the following information:

* [ADBMobileConfig.json Config File Reference](../../configuration/json-config/json-config.md#section_5AD4EDF87E304980B4AC4A5657FDA8B9) 
* [Sample ADBMobileConfig.json File](../../configuration/json-config/json-config.md#section_4655EF79744649E5A5AE19E3224C472C) 
* [Messages description](../../configuration/json-config/json-config.md#section_B97D654BA92149CE91F525268D7AD71F)

## ADBMobileConfig.json Config File Reference {#section_5AD4EDF87E304980B4AC4A5657FDA8B9}

The same config file can be used for your app across multiple platforms:

>[!TIP]
>
>In **Android**, the [!DNL ADBMobileConfig.json] file must be placed in the [!DNL assets] folder.

<table id="table_4068E4D18FA043DA902A2B67731348F2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col02" class="entry"> Minimum SDK Version </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>acquisition </p> </td> 
   <td colname="col02"> 4.1 </td> 
   <td colname="col2"> <p>Enables mobile app acquisition. </p> <p> 
     <ul id="ul_811D701D9DF246289CA719ABEC42784B"> 
      <li id="li_73704A5583BF4E41AA5D0EDFF2158D94"> <span class="codeph"> server </span>, which is the acquisition server that is checked at the initial launch for an acquisition referrer. </li> 
      <li id="li_981270F54556419F87EEBF76EA3BAB4B"> <span class="codeph"> appid </span>, which is the generated ID that uniquely identifies this app on the acquisition server. </li> 
     </ul> </p> <p>If this section is missing, enable Mobile App acquisition and download the SDK configuration file again. For more information, see the <i>referrerTimeout</i> row in this table. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>analyticsForwardingEnabled </p> </td> 
   <td colname="col02"> 4.8.0 </td> 
   <td colname="col2"> <p>The default value is <span class="codeph"> false </span>. </p> <p>The property in the <span class="codeph"> audienceManager </span> object. If <span class="keyword"> Audience Manager </span> is configured, and <span class="codeph"> analyticsForwardingEnabled </span> is set to <span class="codeph"> true </span>, all <span class="keyword"> Analytics </span> traffic is also forwarded to <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>backdateSessionInfo </p> </td> 
   <td colname="col02"> 4.6 </td> 
   <td colname="col2"> <p>Enables/disables the ability for the Adobe SDK to backdate session info hits. </p> <p>Session info hits currently consist of crashes and session length and can be enabled or disabled. </p> <p><b>Enabling or Disabling Hits</b> </p> <p> 
     <ul id="ul_E5ECCD247EF440C797C9E563F0C73EA5"> 
      <li id="li_40DCF27F84A242D1A645D02A226D4613">If you set the value to <span class="codeph"> false </span>, the hits are <b>disabled</b>. <p>The SDK returns to its pre-4.1 behavior of lumping the session information for the previous session with the first hit of the subsequent session. The Adobe SDK also attaches the session info to the current lifecycle, which avoids the creation of an inflated visit. Because inflated visits are no longer created, an immediate drop in visit counts occurs. </p> </li> 
      <li id="li_1FCD2E45B4AE4F088ECB95729CFED9DF">If you do not provide a value, the default value is <span class="codeph"> true </span>, and hits are <b>enabled</b>. <p>When the hits are enabled, the Adobe SDK backdates the session info hit to 1 second after the final hit in the previous session. This means that crash and session data will correlate with the correct date on which they occurred. One side effect is that the SDK might create a visit for the backdated hit. </p> <p>One hit is backdated on every new launch of the application. </p> </li> 
     </ul> </p> <p> <p>Important:  Backdated session hit information is sent in a session info server call, and additional server calls might apply. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>batchLimit </p> </td> 
   <td colname="col02"> 4.1 </td> 
   <td colname="col2"> <p>Threshold for number of hits to be sent in consecutive calls. </p> <p>For example, if <span class="codeph"> batchLimit </span> is set to 10, each hit before the 10th hit will be stored in the queue. When the 10th hit comes in, all 10 hits will be sent consecutively. </p> <p>Remember the following information: </p> <p> 
     <ul id="ul_387F2B726A424EDABCD773672B98FE2F"> 
      <li id="li_29AB735F0340466AB338CA831B558E81">Default value is <span class="codeph"> 0 </span>, which means that batching not enabled. </li> 
      <li id="li_1A619C2A95A64B7BB98442CF28B82436">Requires <span class="codeph"> offlineEnabled = true </span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>charset </p> </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p>Defines the character set that you are using for the data that is sent to Analytics. </p> <p>The charset is used to convert incoming data into UTF-8 for storage and reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>clientCode </p> </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p> <p>Important:  This variable is required by Target. </p> </p> <p>Your assigned client code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>coopUnsafe </p> </td> 
   <td colname="col02"> 4.16.1 </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FFC46EE20E7746E880B9E518A73A1AEB"> 
      <li id="li_516C0638B88649B9B65FF138BB64E7D3"> <p>The Boolean property of the <span class="codeph"> marketingCloud </span> object that, when set to <span class="codeph"> true </span>, will cause device to be opted-out of the Experience Cloud's Device Co-Op. </p> </li> 
      <li id="li_0261EBA5E60B4B219FE146A135E9741F"> <p>Default value is <span class="codeph"> false </span>. </p> </li> 
      <li id="li_E4B4489CFCA6489C90F6FF578E558A85">This setting is used <b>only</b> for Device Co-op provisioned customers. </li> 
     </ul> </p> <p>For Device Co-op members who require this value set to <span class="codeph"> true </span>, you need to work with the Co-op team to request a blacklist flag on your Device Co-op account. There is no self-service path to enabling these flags. </p> <p>Remember the following information: </p> <p> 
     <ul id="ul_7BC266FE29734E1BAA642DAA87770A24"> 
      <li id="li_B0CB809AF3BF4B5E957DE7690593E11A">When <span class="codeph"> coopUnsafe </span> is set to <span class="codeph"> true </span>, <span class="codeph"> coop_unsafe=1 </span> will always be appended to Audience Manager and Visitor ID hits. </li> 
      <li id="li_C19A3CA8075046AFA95331449E898D5C">If you enable Analytics server-side forwarding to Audience Manager, you will also see <span class="codeph"> coop_unsafe=1 </span> on Analytics hits. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> environmentId </td> 
   <td colname="col02"> 4.14 </td> 
   <td colname="col2"> <p>The ID of the environment you want to use. </p> <p>You can specify a valid ID ( <span class="codeph"> environmentId=8 </span>), and if <span class="codeph"> environmentId </span> is not included, the default Production environment is used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>lifecycleTimeout </p> </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p>Default value is 300 seconds. </p> <p>Specifies the length of time, in seconds, that must elapse between the time the app launches but before the launch is considered to be a new session. This timeout also applies when your application is sent to the background and reactivated. </p> <p>The time that your app spends in the background is not included in the session length. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>messages </p> </td> 
   <td colname="col02"> 4.2 </td> 
   <td colname="col2"> <p>Generated automatically by Adobe Mobile services, defines the settings for in-app messaging. For more information, see the <i>Messages Description</i> section below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineEnabled </p> </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p>When enabled, hits are queued while the device is offline and sent later when the device is online. Your report suite must be timestamp-enabled to use offline tracking. </p> <p>The default value is <span class="codeph"> false </span>. </p> <p> <p>Important:  If timestamps are enabled on your report suite, your <span class="codeph"> offlineEnabled </span> configuration property <i>must</i> be true. if your report suite is not timestamp enabled, your <span class="codeph"> offlineEnabled </span> configuration property <i>must</i> be false. If this is not configured correctly, data will be lost. If you are not sure whether a report suite is timestamp enabled, contact Customer Care or download the configuration file from Adobe Mobile services. </p> </p> <p>If you are currently reporting AppMeasurement data to a report suite that also collects data from JavaScript, you might need to set up a separate report suite for mobile data or include a custom timestamp on all JavaScript hits that use the <span class="codeph"> s.timestamp </span> variable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>org </p> </td> 
   <td colname="col02"> 4.3 </td> 
   <td colname="col2"> <p>Specifies the Experience Cloud org ID for the ID service. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>poi </p> </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p>Each point of interest (POI) array holds the POI name, latitude, longitude, and radius in meters for the area of the point. The POI name can be any string. </p> <p>When a <span class="codeph"> trackLocation </span> call is sent, if the current coordinates are within a defined POI, a context data variable is populated and sent with the <span class="codeph"> trackLocation </span> call. </p> 
    <codeblock class="syntax javascript">
      "poi"&nbsp;:&nbsp;[&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;["san&nbsp;francisco",37.757144,-122.44812,7000],&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;["santa&nbsp;cruz",36.972935,-122.01725,600]&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;] 
    </codeblock> <p>Tip:  Starting in version 4.2, POIs are defined in the Adobe Mobile interface and synchronized dynamically to the app configuration file. This synchronization requires the <span class="codeph"> analytics.poi </span> setting: 
     <codeblock class="syntax javascript">
       “analytics.poi”:&amp;nbsp;`“https://assets.adobedtm.com/…/yourfile.json”`, 
     </codeblock> <p>If this setting is not configured, the <span class="codeph"> ADBMobile.json </span> file must be updated to include this line. To download an updated configuration file, see <a href="../../getting-started/requirements.md#concept_2FA4E790CA1646FFB44488CF017821DE" format="dita" scope="local"> Before You Start </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>postback </p> </td> 
   <td colname="col02"> 4.6 </td> 
   <td colname="col2"> <p>Here is the definition for the "callback" message template: </p> 
    <codeblock class="syntax javascript">
      "payload":&nbsp;{&nbsp;"templateurl":&nbsp;"",&nbsp;//&nbsp;required&nbsp;-&nbsp;will&nbsp;be&nbsp;token-expanded&nbsp;prior&nbsp;to&nbsp;being&nbsp;sent&nbsp;"templatebody":&nbsp;"",&nbsp;//&nbsp;optional&nbsp;-&nbsp;if&nbsp;this&nbsp;length&nbsp;&gt;&nbsp;0&nbsp;POST&nbsp;will&nbsp;be&nbsp;used&nbsp;as&nbsp;transport&nbsp;method.&nbsp;This&nbsp;is&nbsp;a&nbsp;base64&nbsp;encoded&nbsp;blob,&nbsp;which&nbsp;will&nbsp;be&nbsp;decoded&nbsp;and&nbsp;token-expanded&nbsp;prior&nbsp;to&nbsp;being&nbsp;sent.&nbsp;"contenttype":&nbsp;"",&nbsp;//&nbsp;optional&nbsp;-&nbsp;if&nbsp;this&nbsp;is&nbsp;length&nbsp;&gt;&nbsp;0&nbsp;and&nbsp;POST&nbsp;type&nbsp;is&nbsp;selected&nbsp;this&nbsp;will&nbsp;be&nbsp;set&nbsp;as&nbsp;the&nbsp;Content-Type&nbsp;header.&nbsp;&nbsp;if&nbsp;this&nbsp;is&nbsp;not&nbsp;supplied&nbsp;for&nbsp;a&nbsp;POST&nbsp;request,&nbsp;the&nbsp;default&nbsp;will&nbsp;be&nbsp;"application/x-www-form-urlencoded"&nbsp;"timeout":&nbsp;0&nbsp;//&nbsp;optional&nbsp;-&nbsp;number&nbsp;of&nbsp;seconds&nbsp;to&nbsp;wait&nbsp;before&nbsp;timing&nbsp;out.&nbsp;&nbsp;Default&nbsp;is&nbsp;2.} 
    </codeblock> <p>The <span class="codeph"> payload </span> object in the code is a sample payload for a message definition that goes in <span class="codeph"> ADBMobileConfig.json </span>. </p> <p>For more information, one of the following: </p> <p> 
     <ul id="ul_2BA58784B6394C7491F701C56209C237"> 
      <li id="li_B47C5BE7B9A54DADAB38ADB58B7F5B2A"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/postbacks.html" format="https" scope="external"> Postbacks </a> (Android) </p> </li> 
      <li id="li_125D57A2CFEB4B9F980149968DEF0345"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/postback.html" format="https" scope="external"> Postbacks </a> (iOS) </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>privacyDefault </p> </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p>The default value is <span class="codeph"> optedin </span>. </p> <p> 
     <ul id="ul_B7A92BD8C9BA4EFEA5CCD451A76042BD"> 
      <li id="li_B6F78E8FE4DD4872B3DC2FBA656DBCDE"> For <span class="codeph"> optedin </span>, the hits are sent immediately. </li> 
      <li id="li_EF1EF12AF30C4E8D86F0F62E37F1B90E">For <span class="codeph"> optedout </span>, the hits are discarded. </li> 
      <li id="li_BBF64ECCC33B40519F9C4221077C12A1">For <span class="codeph"> optunknown </span>, if your report suite is timestamp-enabled, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded). <p>If your report suite is not timestamp-enabled, hits are discarded until the privacy status changes to opt in. </p> </li> 
     </ul> </p> <p>This only sets the initial value. If this value is set or changed in code, the new value is used until it is changed again, or when the app is uninstalled and reinstalled. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" id="referrerTimeout"> <p>referrerTimeout </p> </td> 
   <td colname="col02"> 4.1 </td> 
   <td colname="col2"> <p>Number of seconds the SDK waits for acquisition referrer data on the initial launch before timing out. If you are using acquisition, we recommend a 5-second timeout. </p> <p>Important:  This variable is required by Acquisition. </p> <p>If the variable is set to <span class="codeph"> 0 </span> or is not included, the SDK does not wait for acquisition data, and acquisition metrics are not tracked. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>remotes </p> </td> 
   <td colname="col02"> 4.2 </td> 
   <td colname="col2"> <p>Configured automatically and defines the Adobe-hosted endpoints for dynamic configuration files. The last update time of each configuration file is checked against the current version at each launch, and the updates are downloaded and saved. </p> <p> 
     <ul id="ul_5A20F30E8BD245958B3D7E86A3D6803E"> 
      <li id="li_D6CE65D30FFB421CB5F0D30724DAA847"> <span class="codeph"> analytics.poi </span> is the endpoint for hosted POI configuration. </li> 
      <li id="li_C8FEFBAB3A4B4B269DECB3E4F8391E5B"> <span class="codeph"> messages </span> is the endpoint for hosted in-app message configuration. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>rsids </p> </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p> <p>Important:  This variable is required by Analytics. </p> </p> <p>One or more report suites to receive Analytics data. Multiple report suite IDs should be comma-separated with no space between. 
     <codeblock class="syntax javascript">
       "rsids"&amp;nbsp;:&amp;nbsp;"rsid" 
     </codeblock> 
     <codeblock class="syntax javascript">
       "rsids"&amp;nbsp;:&amp;nbsp;"rsid1,rsid2" 
     </codeblock> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> server </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p> <p>Important:  This variable is required by Analytics and/or Audience Management. </p> </p> <p>The Analytics or Audience Management server, based on the parent node. </p> <p> This variable should be populated with the server domain, without an <span class="filepath"> https:// </span> or <span class="filepath"> https:// </span> protocol prefix. This prefix is handled automatically by the library and is based on the <span class="codeph"> ssl </span> variable. </p> <p> If <span class="codeph"> ssl </span> is <span class="codeph"> true </span>, a secure connection is made to this server. If <span class="codeph"> ssl </span> is <span class="codeph"> false </span>, a non-secure connection is made to this server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ssl </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p>The default value is <span class="codeph"> false </span>. </p> <p>Enables ( <span class="codeph"> true </span>) or disables ( <span class="codeph"> false </span>) the ability to send measurement data by using SSL (HTTPS). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col02"> </td> 
   <td colname="col2"> <p>The definition for the "callback" message template is shown below: </p> 
    <codeblock class="syntax javascript">
      "payload":&nbsp;{&nbsp;"templateurl":&nbsp;"",&nbsp;//&nbsp;required&nbsp;-&nbsp;will&nbsp;be&nbsp;token-expanded&nbsp;prior&nbsp;to&nbsp;being&nbsp;sent&nbsp;"templatebody":&nbsp;"",&nbsp;//&nbsp;optional&nbsp;-&nbsp;if&nbsp;this&nbsp;length&nbsp;&gt;&nbsp;0&nbsp;POST&nbsp;will&nbsp;be&nbsp;used&nbsp;as&nbsp;transport&nbsp;method.&nbsp;This&nbsp;is&nbsp;a&nbsp;base64&nbsp;encoded&nbsp;blob,&nbsp;which&nbsp;will&nbsp;be&nbsp;decoded&nbsp;and&nbsp;token-expanded&nbsp;prior&nbsp;to&nbsp;being&nbsp;sent.&nbsp;"contenttype":&nbsp;"",&nbsp;//&nbsp;optional&nbsp;-&nbsp;if&nbsp;this&nbsp;is&nbsp;length&nbsp;&gt;&nbsp;0&nbsp;and&nbsp;POST&nbsp;type&nbsp;is&nbsp;selected&nbsp;this&nbsp;will&nbsp;be&nbsp;set&nbsp;as&nbsp;the&nbsp;Content-Type&nbsp;header.&nbsp;&nbsp;if&nbsp;this&nbsp;is&nbsp;not&nbsp;supplied&nbsp;for&nbsp;a&nbsp;POST&nbsp;request,&nbsp;the&nbsp;default&nbsp;will&nbsp;be&nbsp;"application/x-www-form-urlencoded"&nbsp;"timeout":&nbsp;0&nbsp;//&nbsp;optional&nbsp;-&nbsp;number&nbsp;of&nbsp;seconds&nbsp;to&nbsp;wait&nbsp;before&nbsp;timing&nbsp;out.&nbsp;&nbsp;Default&nbsp;is&nbsp;2.} 
    </codeblock> <p>The <span class="codeph"> payload </span> object in the code is an sample payload for a message definition that goes in <span class="codeph"> ADBMobileConfig.json </span>. </p> <p>For more information, see the relevant topic: </p> <p> 
     <ul id="ul_25ED1943265846009B9C2BA31C75C3FB"> 
      <li id="li_11BF64056A26429A97F36CB62DDB79F2"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/postbacks.html" format="https" scope="external"> Postbacks </a> (Android) </p> </li> 
      <li id="li_5DC6AAA8E10646B4A0F4449391A6083F"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/postback.html" format="https" scope="external"> Postbacks </a> (iOS) </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> timeout </td> 
   <td colname="col02"> 4.0 </td> 
   <td colname="col2"> <p>Determines how long Target waits for a response. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample ADBMobileConfig.json File {#section_4655EF79744649E5A5AE19E3224C472C}

Here is a sample `ADBMobileConfig.json` file:

```js
{ 
    "version": "2014-08-05T19:18:28.169Z", 
    "marketingCloud" : { 
        "org": "016D5C175213CCA80A490D05@AdobeOrg", 
        "coopUnsafe": false 
    }, 
    "target": { 
        "clientCode": "", 
        "timeout": 5, 
        "environmentId": 8 
    }, 
    "audienceManager": { 
        "server": "", 
        "analyticsForwardingEnabled": false 
    }, 
    "acquisition": { 
        "server": "c00.adobe.com", 
        "appid": "10a77a60192fbb628376e1b1daeeb65debf934e2c807e067ceb2963a41b165ee" 
    }, 
    "analytics": { 
        "rsids": "coolApp", 
        "server": "my.CoolApp.com", 
        "ssl": false, 
        "offlineEnabled": true, 
        "charset": "UTF-8", 
        "lifecycleTimeout": 300, 
        "privacyDefault": "optedin", 
        "batchLimit": 0, 
        "referrerTimeout": 5, 
        "poi": [ 
            ["san francisco",37.757144,-122.44812,7000],  
            ["santa cruz",36.972935,-122.01725,600] 
        ] 
    }, 
    "messages": [ 
        { 
            "messageId": "cb426565-a563-497a-a889-9dbeb451f8ae", 
            "template": "fullscreen", 
            "payload": { 
                 "html": "<!DOCTYPE html><html><head><meta charset=\"utf-8\" /><title></title><style></style></head><body><iframe src=\"https://www.adobe.com/\" frameborder=\"0\"></iframe></body></html>" 
            }, 
            "showOffline": false, 
            "showRule": "always", 
            "endDate": 2524730400, 
            "startDate": 0, 
            "audiences": [], 
            "triggers": [ 
                { 
                    "key": "pev2", 
                    "matches": "eq", 
                    "values": [ 
                        "AMACTION:custom" 
                    ] 
                } 
            ] 
        } 
    ], 
    "remotes": { 
        "analytics.poi": "https://assets.adobedtm.com/staging/42a6fc9b77cd9f29082cf19b787bae75b7d1f9ca/scripts/satellite-53e0faadc2f9ed92bc00003b.json", 
        "messages": "https://assets.adobedtm.com/staging/42a6fc9b77cd9f29082cf19b787bae75b7d1f9ca/scripts/satellite-53e0f9e2c2f9ed92bc000032.json" 
    } 
}
```

## Messages description {#section_B97D654BA92149CE91F525268D7AD71F}

The messages node is generated automatically by Adobe Mobile services and typically does not need to be manually changed. The following description is provided for troubleshooting purposes:

* "messageId" 
* Generated ID, required 
* "template"

    * "alert", "fullscreen", or "local" 
    * required

* "showOffline"

    * true or false 
    * default is false

* "showRule"

    * "always", "once", or "untilClick" 
    * required

* "endDate"

    * number of seconds since Jan 1, 1970 
    * default is 2524730400

* "startDate"

    * number of seconds since Jan 1, 1970 
    * default is 0

* "payload"

    * "html" 

        * fullscreen template only, required 
        * html defining the message

    * "image"

        * fullscreen only, optional 
        * url to the image to be used for a fullscreen image

    * "altImage"

        * fullscreen only, optional 
        * name of the bundled image to use if the url specified in

            * image 
            * is unreachable

    * "title"

        * fullscreen and alert, required 
        * title text for a fullscreen or alert message

    * "content"

        * alert and local notification, required 
        * sub-text for an alert message, or notification text for a local notification message

    * "confirm"

        * alert, optional 
        * text used in the confirm button

    * "cancel"

        * alert, required 
        * text used in the cancel button

    * "url"

        * alert, optional 
        * url action to load if the confirm button is clicked

    * "wait"

        * local notification, required 
        * amount of time to wait (in seconds) to post the local notification after matching its criteria

* "audiences"

    * array of objects that defines how the message should be shown 
    * "key"

        * variable name to look for in the hit, required

    * "matches"

        * type of matcher used when doing the comparison 

            * eq = equals 
            * ne = does not equal 
            * co = contains 
            * nc = does not contain 
            * sw = starts with 
            * ew = ends with 
            * ex = exists 
            * nx = does not exist 
            * lt = less than 
            * le = less than or equals 
            * gt = greater than 
            * ge = greater than or equals

    * "values"

        * an array of values used to match against the value of the variable named in

          key

          with the matcher type in

          matches

* "triggers"

    * same as audiences, but this is the action instead of the audience 
    * "key" 
    * "matches" 
    * "values"
