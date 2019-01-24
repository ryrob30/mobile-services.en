---
description: You can use iOS PhoneGap Plug-in methods to complete a variety of tasks.
keywords: android;library;mobile;sdk
seo-description: You can use iOS PhoneGap Plug-in methods to complete a variety of tasks.
seo-title: PhoneGap Plug-in Methods
solution: Marketing Cloud,Analytics
title: PhoneGap Plug-in Methods
topic: Developer and implementation
uuid: bc3db9ce-81b7-45ec-88aa-6020c1db5d9c
---

# PhoneGap Plug-in Methods{#phonegap-plug-in-methods}

You can use iOS PhoneGap Plug-in methods to complete a variety of tasks.

Here is a link of the iOS PhoneGap Plug-in methods:

* Configuration 
* Tracking 
* Target 
* Acquisition 
* Audience Manager 
* ID Service 
* App Extensions 
* Apple Watch Methods

In `html` files where you want to use tracking, add the following to the `<head>` tag:

```
<script type="text/javascript" charset="utf-8" src="ADB_Helper.js"></script>
```

## Configuration Methods {#section_CC429F68292D4601AEEF0A91445E1185}

* **getPrivacyStatus**

  Returns the privacy status for current user. 
  
  Here are the available statuses: 
  
  * `ADB.optedIn`: The hits are sent immediately. 
  * `ADB.optedOut`: The hits are discarded. 
  * `ADB.optUnknown`: If your report suite **is** timestamp-enabled, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded). If your report suite **is not** timestamp-enabled, hits are discarded until the privacy status changes to opt in. 

    The default value is set in `ADBMobileConfig.json`. 

  * Here is the code sample for this method:

    ```java
    getPrivacyStatus(function (value) { myTempVal = value; }, function () {myTempVal = null;}); 
    ```
* **setPrivacyStatus**

  Sets the privacy status for the current user to `status`.

  You can set one of the following statuses: 
  
  * `ADB.optedIn`: The hits are sent immediately.  
  * `ADB.optedOut`: The hits are discarded. 
  * `ADB.optUnknown`: If your report suite **is** timestamp-enabled, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded). If your report suite **is not** timestamp-enabled, hits are discarded until the privacy status changes to opt in. 

  * Here is the code sample for this method:

    ```java
    ADB.setPrivacyStatus('ADB.optedIn');
    ```
* **getLifetimeValue**

  Returns the lifetime value of the current user. The default value is 0.

  * Here is the code sample for this method:

    ```java
    ADB.getLifetimeValue(function (value) { myTempVal = value }, function () { myTempVal = null; }); 
    ```

* **setDebugLogging**

  Enables (`true`) or disables (`false`) viewing debug information. By default, this variable is `false`.

  * Here is the code sample for this method:

    ```java
    ADB.setDebugLogging(true);
    ```

* **getVersion**

  Gets the library version. 

  * Here is the code sample for this method:

    ```java
    ADB.getVersion(function (value) { versionNum = value }, function () { versionNum = 1.0;});
    ```
* **trackingIdentifier**

  Returns the automatically generated visitor identifier.
  
  This is an app-specific, unique visitor ID that is generated when the app is initially launched and is stored and used from that point. This ID is preserved between app upgrades and is removed when the app is uninstalled.
  
  >[!TIP]
  >
  >If your app upgrades from the Experience Cloud 3.x to 4.x SDK, the previous visitor ID (custom or automatically generated) is retrieved and stored as the custom user identifier. For more information, see `getUserIdentifier` below. This ID preserves visitor data between SDK upgrades. 
  
  For new installations on the 4.x SDK, the user identifier is `null` and tracking identifier is used. 

  * Here is the code sample for this method:

    ```java
    ADB.trackingIdentifier(function (value) { myTempVal = value; }, function () { myTempVal = null; }); 
    ```
* **getUserIdentifier**

  If a customer user identifier has been set, returns this identifier; if the identifier has not been set, returns `null`. The default value is `null`.

  * Here is the code sample for this method:

    ```java
    getUserIdentifier(function(value) { myTempVal = value; }, function () { myTempVal = null; });
    ```

* **setUserIdentifier**

  Sets the user identifier to `identifier`. 

  * Here is the code sample for this method:

    ```java
    ADB.setUserIdentifier('testUser');
    ```
* **setPushIdentifier**

  Sets the device token for push notifications.

    ```java
    getUserIdentifier(function (value) { myTempVal = value; }, function () { myTempVal = null; });
    ``` 

  * Here is the syntax for this method:

    ```java
    ADB.setPushIdentifier(pushIdentifier, success, fail);
    ```

  * Here is the code sample for this method:

    ```java
    ADB.setPushIdentifier('test_push_identifier',function (value) { alert('success'); },function (value) { alert('fail'); }); 
    ```

* **keepLifecycleSessionAlive**

  Sets the preference of lifecycle session keep alive.

  >[!IMPORTANT]
  >
  >Calling `keepLifecycleSessionAlive` prevents your app from launching a new session the next time it is resumed from background. You should only use this method if your app registers for notifications in the background. 

  * Here is the code sample for this method:

    ```js
    ADB.keepLifecycleSessionAlive(); 
    ```
* **trackingSendQueuedHits**

  Forces the library to send all queued hits regardless of current batch options. 

  * Here is the code sample for this method:

    ```js
    ADB.trackingSendQueuedHits();
    ```

* **trackingGetQueueSize** 

  Gets or sets the number of stored tracking calls in the offline queue. 

  * Here is the code sample for this method:

    ```js
    ADB.trackingGetQueueSize(function (value) { myTempVal = value;}, function () { myTempVal = null;}); 
    ```
* **trackingClearQueue**

  Removes all stored tracking calls from the offline queue.

  >[!WARNING]
  >
  >Be careful when clearing the queue manually, because it cannot be reversed. 

  * Here is the code sample for this method:

    ```js
    ADB.trackingClearQueue(function (value) { myTempVal = value; }, function () { myTempVal = null; }); 

## PII Methods {#section_DB27270D2CEB4D369E0090FD9D1A7F81}

* **collectPII**

  Submits a PII collection request.

  * Here is the syntax for this method:

  ```javascript
  ADB.collectPII(piiData,success, fail);
  ```

  * Here is the code sample for this method:

    ```javascript
    ADB.collectPII({'k1':'v1','k2':'v2','k3':'v3'}, function (value) { alert('success') },function (value) { alert('fail') ;});

## Tracking Methods {#section_7946BB753A4446FE8A3ED728AEF97D04}

* **trackAdobeDeepLink**

  Tracks an Adobe Deep Link click-through.

  >[!TIP]
  >
  >If the Lifecycle call is a launch event, the Adobe Link data will be appended, otherwise an extra call will be sent. 

  * Here is the syntax for this method:

    ```js
    ADB.trackAdobeDeepLink(deeplinkURL, success, fail); 
    ```

  * Here is the code sample for this method:

    ```js
    ADB.trackAdobeDeepLink('xyz-deeplink-url',function (value) { alert('success'); },function (value) { alert('fail') }); 
    ```
* **trackState**

  Tracks an app state with optional context data. States are the views that are available in your app, such as such as `home dashboard`, `app settings`, `cart`, and so on. These states are similar to pages on a website, and `trackState` calls increment page views. 
  
  `cData`: JSON object with key-value pairs to send in context data. 

  * Here is the syntax for this method:

    ```js
    ADB.trackState(string stateName[,JSON cData]);
    ```
  * Here are code samples for this method:

    ```js
      ADB.trackState("login&amp;nbsp;page"); 
      ```
    ```js
      ADB.trackState("login page", {"user":"john","remember":"true"});
      ```
* **trackAction**

  Tracks an action in your app. Actions include `logins`, `banner taps`, `feed subscriptions`, and other metrics that occur in your app and that you want to measure. 

  * Here is the syntax for this method:

    ```js
    ADB.trackAction(string action[,JSON cData]); 
    ```
  * Here are the code samples for this method:

    ```js
      ADB.trackAction("login");
    ```

    ```js
      ADB.trackAction("login", {"user":"john","remember":"true"}); 
    ```
* **trackLocation**

  Sends the current x y coordinates. Also uses points of interest defined in the `ADBMobileConfig.json` file to determine if the location provided as a parameter is within any of your POI. If the current coordinates are within a defined POI, a context data variable is populated and sent with the `trackLocation` call.

  * Here is the syntax for this method:

    ```java
    ADB.trackLocation(x, y[,JSON cData]); 
    ```
  * Here is the code sample for this method:

    ```java
    ADB.trackLocation('40.431596', '-111.893713'); 
    ```

* **trackLifetime​ValueIncrease**

  Adds `amount` to the user's lifetime value. 

  * Here is the syntax for this method:

    ```java
    ADB.trackLifetimeValueIncrease(amount[,JSON&amp;nbsp;cData]); 
    ```

  * Here is the code sample for this method:

    ```java
    ADB.trackLifetimeValueIncrease('10.01'); 
    ```

* **trackTimed​ActionStart**

  Start a timed action with the name `action`. 
  
  If you call this method for an action that has already started, the previous timed action is overwritten. 
  
  >[!TIP]
  >
  >This call does not send a hit. 

  * Here is the syntax for this method:

    ```java
    ADB.trackTimedActionStart(action[,JSON&amp;nbsp;cData]);
    ```

  * Here is the code sample for this method:

    ```java
    ADB.trackTimedActionStart("cartToCheckout"); 
    ```
* **trackTimed​ActionUpdate**

  Pass in `cData` to update the context data that is associated with the `action`>. 
  
  The `cData` that is passed is appended to the existing data for the action and, if the same key is already defined for `action`, overwrites the data.

  * Here is the syntax for this method:

    ```java
    ADB.trackTimedActionUpdate(String action[,JSON cData]);
    ```

  * Here is the code sample for this method:

    ```java
    ADB.trackTimedActionUpdate("cartToCheckout",{'SampleContextDataKey3':'SampleContextDataVal3','SampleContextDataKey4':'SampleContextDataVal4'});
    ```
* **trackTimed​ActionEnd**

  End a timed action. 

  * Here is the code sample for this method:

    ```java
    ADB.trackTimedActionEnd("cartToCheckout"); 
    ```

* **trackingTimedActionExists**

  Returns whether a timed action is in progress. 

  * Here is the syntax for this method:

    ```java
    ADB.trackingTimedActionExists(function (value) { myTempVal = value }, function () { myTempVal = null; }); 
    ```

## Beacon Methods {#section_F9500D6BD95348E08E283C02B657019D}

* **trackBeacon**

  Tracks when a user enters the proximity of a beacon. 

  * Here is the syntax for this method:

    ```js
    ADB.trackBeacon(uuid, major, minor, proximity, cData) 
    ```
  * Here is the code sample for this method:

    ```js
    ADB.trackBeacon('2F234454-CF6D-4A0F-ADF2-F4911BA9FFA6', 1, 2, 
    ADB.beaconUnknown, {'hp':'hp_val','hp.company':'adobe'}
    ```
* **clearCurrentBeacon**

  Clears the beacon data after a user leaves the proximity of the beacon. 

  * Here is the syntax for this method:

    ```js
    ADB.clearCurrentBeacon(success, fail) 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADB.clearCurrentBeacon(); 
      ```

## Target Methods {#section_8670140C5A3F455E887830AFFDF91D59}

* **targetLoadRequest**

  Sends a request to your configured `Target` server and returns the string value of the offer. 

  * Here is the syntax for this method:

    ```java
    ADB.targetLoadRequest(success, fail, name, defaultContent, parameters);
    ```
  * Here is the code sample for this method:

    ```java
    ADB.targetLoadRequest(function&nbsp;(value)
    {myTempVal = value }, function () { myTempVal = null;},'bannerOffer', 'none', {'hp':'hp_val_new','hp.company':'adobe', 'hp.val2':'hp_val2'}); 
    ```
* **targetLoadOrderConfirmRequest**
  
  Sends a request to your configured `Target` server.

  * Here is the syntax for this method:

    ```java
    ADB.targetLoadOrderConfirmRequest(success, fail name orderId, orderTotal, productPurchaseId, parameters); 
    ```

  * Here is the syntax for this method:

    ```java
    ADB.targetLoadRequest(function (value) { myTempVal = value }
    , function ()
    { myTempVal = null; } 
    , 'name' 'orderId' 'total', 'purchaseId',
    {'hp':'hp_val_new','hp.company':'adobe', 'hp.val2':'hp_val2'}
    ); 
    ```
* **targetClearCookies**

  Clears the `Target`cookies from shared cookie storage. 

  * Here is the code sample for this method:

    ```java
    ADB.targetClearCookies(); 
    ```
* **targetLoadRequestWithNameWithLocationParameters**

  Processes a `Target` service request. 

  * Here is the syntax for this method:

    ```java
    ADB.targetLoadRequestWithNameWithLocationParameters(
      success, fail, name, defaultContent, profileParameters, orderParameters, mboxParameters requestLocationParameters
      ); 
    ```
  * Here is the code sample for this method:

    ```java
    ADB.targetLoadRequestWithNameWithLocationParameters  (function () { alert('success'); }, function () { alert('fail'); }, ;'bannerOffer', 'none', {'hp':'hp_val_new','hp.company':'adobe', 'hp.val2':'hp_val2'}, {'hp':'hp_val_new','hp.company':'adobe', 'hp.val2':'hp_val2'},{'hp':'hp_val_new','hp.company':'adobe', 'hp.val2':'hp_val2'},{'hp':'hp_val_new','hp.company':'adobe', 'hp.val2':'hp_val2'});
    ```


<table id="table_258F21CC9F1A459597E95D7BFEEE2ACE"> 
 <thead> 
   <td colname="col1"> <p>targetLoadRequestWithName </p> </td> 
   <td colname="col2"> <p> Processes a <span class="keyword"> Target </span> service request. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadRequestWithRequestLocationParams(success,&nbsp;fail,&nbsp;name,&nbsp;defaultContent,&nbsp;profileParameters,&nbsp;orderParameters,&nbsp;mboxParameters,&nbsp;requestLocationParameters); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetLoadRequestWithRequestLocationParams(function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;},&amp;nbsp;'bannerOffer',&amp;nbsp;'none',&amp;nbsp;{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'},&amp;nbsp;{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'},{'hp':'hp_val_new','hp.company':'adobe',&amp;nbsp;'hp.val2':'hp_val2'}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetSessionID </p> </td> 
   <td colname="col2"> <p> Gets the value of the <span class="codeph"> SessionID </span> cookie returned for this visitor by the <span class="keyword"> Target </span>server. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetSessionID&amp;nbsp;(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetSessionID(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert(value);&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetPcID </p> </td> 
   <td colname="col2"> <p> Gets the value of the <span class="codeph"> PcID </span> cookie that is returned for this visitor by the <span class="keyword"> Target </span> server. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetPcID&amp;nbsp;(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetPcID(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert(value);&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetSetThirdPartyID </p> </td> 
   <td colname="col2"> <p> Sets the custom visitor ID for <span class="keyword"> Target </span>. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetSetThirdPartyID(thirdPartyID,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.targetSetThirdPartyID('test-third-party-id',&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>targetThirdPartyID </p> </td> 
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
   <td colname="col2"> <p>Sends a request to your configured <span class="keyword"> Target </span> server and returns the string value of the offer. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.acquisitionCampaignStartForApp(appId,&amp;nbsp;data,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p> </p> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.acquisitionCampaignStartForApp(“appId”,&amp;nbsp;{‘key’:‘value’},&amp;nbsp;function()&amp;nbsp;{…},&amp;nbsp;function()&amp;nbsp;{…})); 
    </codeblock> <p> </p> 
    <codeblock class="syntax java">
      ADB.acquisitionCampaignStartForApp(“appId”,&amp;nbsp;{‘key’:‘value’});&amp;nbsp; 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

## Advertising Identifier {#section_194607D101B047A19C51B19E176E1500}

In the main activity that is generated by Cordova, call `Config.submitAdvertisingIdentifierTask()` in the `onResume()` method. For more information, see [Configuration Methods](../configuration/methods.md#concept_12F12E3E0E434F8CB997AF4027810EBF).

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
   <td colname="col2"> <p>Processes an <span class="keyword"> Audience Manager </span> service request. </p> <p><b>Syntax:</b> </p> 
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
   <td colname="col2"> <p>Resets <span class="keyword"> Audience Manager </span> UUID and purges the current visitor profile. </p> <p><b>Example:</b> </p> 
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
   <td colname="col2"> <p>Returns the Experience Cloud ID from the ID Service. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorGetMarketingCloudId(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorGetMarketingCloudId(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;value;&amp;nbsp;},&amp;nbsp;function&amp;nbsp;()&amp;nbsp;{&amp;nbsp;mcid&amp;nbsp;=&amp;nbsp;null;&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorSyncIdentifiers </p> </td> 
   <td colname="col2"> <p>Synchronizes the provided identifiers with the ID Service. </p> <p><b>Syntax:</b> </p> 
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
   <td colname="col1"> <p>visitorSyncIdentifiersWithAuthenticationState </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifiers to the ID Service. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifiersWithAuthenticationState(identifiers,&nbsp;authenticationState,&nbsp;success,&nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifiersWithAuthenticationState({'k1':'v1','k2':'v2','k3':'v3'},&amp;nbsp;ADB.mobileVisitorAuthenticationStateAuthenticated,&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorSyncIdentifierWithType </p> </td> 
   <td colname="col2"> <p> Synchronizes the provided identifier to the ID Service. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      &nbsp;ADB.visitorSyncIdentifierWithType(identifierType,&nbsp;identifier,&nbsp;authenticationState,&nbsp;success,&nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorSyncIdentifierWithType('test-identifier-type',&amp;nbsp;'test-identifier',&amp;nbsp;ADB.mobileVisitorAuthenticationStateAuthenticated,&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('success');&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorAppendToURL </p> </td> 
   <td colname="col2"> <p> Appends visitor identifiers to the given URL. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorAppendToURL(urlToAppend,&amp;nbsp;success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorAppendToURL('test_visitor_url',&amp;nbsp;function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert(value);&amp;nbsp;},''); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>visitorGetIDs </p> </td> 
   <td colname="col2"> <p> Returns all <span class="codeph"> visitorIDs </span> that have been synced. </p> <p><b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorGetIDs&amp;nbsp;(success,&amp;nbsp;fail); 
    </codeblock> <p><b>Example:</b> </p> 
    <codeblock class="syntax java">
      ADB.visitorGetIDs(function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert(value);&amp;nbsp;},function&amp;nbsp;(value)&amp;nbsp;{&amp;nbsp;alert('fail');&amp;nbsp;}); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>
