---
description: Postbacks allow you to send data that is collected by the SDK to a third-party server. By leveraging the same triggers and traits that you use to display an in-app message, you can configure the SDK to send customized data to a third-party destination.
seo-description: Postbacks allow you to send data that is collected by the SDK to a third-party server. By leveraging the same triggers and traits that you use to display an in-app message, you can configure the SDK to send customized data to a third-party destination.
seo-title: Postbacks
solution: Marketing Cloud,Analytics
title: Postbacks
uuid: 25e2a5fb-1203-40dd-96cd-b23e0f23376d
index: y
internal: n
snippet: y
---

# Postbacks{#postbacks}

Postbacks allow you to send data that is collected by the SDK to a third-party server. By leveraging the same triggers and traits that you use to display an in-app message, you can configure the SDK to send customized data to a third-party destination.

>[!IMPORTANT]
>
>This functionality requires SDK version 4.6.0 or later.

Postback messages are queued and follow all existing online/offline rules that govern analytics data collection. When a message matches (like shown-messages do), postback messages do not cancel the rest of the messages. This allows for multiple postbacks to occur on the same analytics hit. For the definition, see the *postbacks* row in [ADBMobile JSON Config](../../configuration/json-config/json-config.md#concept_105FBD9EBABE4B21BD7D49687AB2D5BA)

## Template Expansions {#section_6758AD05A24C4E9E965F5253294C164A}

Template expansions are available in both the `templateurl` and `templatebody` properties. Template items take the form of `{key}`, where `key` is a context-data key, or traditional data key. The values available for template expansion are limited to the [standard Lifecycle variables list](https://marketing.adobe.com/resources/help/en_US/mobile/ios/metrics.html), in addition to any custom data attached to the hit that triggers the message. No historical-based or segment-based data is available at this time.

There are also specific, reserved templates that the SDK will replace for you automatically with internal data known to the SDK.

This list includes: 

<table id="table_38E463568634440CA72552A6C80168AD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Token Name </th> 
   <th colname="col2" class="entry"> Token Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> {%sdkver%}</span> </p> </td> 
   <td colname="col2"> <p>Returns SDK version. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> {%cachebust%}</span> </p> </td> 
   <td colname="col2"> <p>Resolves to a random number between 1 and 100000000. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> {%adid%}</span> </p> </td> 
   <td colname="col2"> <p>Returns IDFA.
     <!-- and Advertiser ID for Android--> Note, this only works if you have used <span class="codeph"> setAdvertisingIdentifier</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> {%pushid%}</span> </p> </td> 
   <td colname="col2"> <p>Returns the Push Identifier token. Note, this only works if you have used <span class="codeph"> setPushIdentifier</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> {%timestampu%}</span> </p> </td> 
   <td colname="col2"> <p>Returns current timestamp in epoch time. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="codeph"> {%timestampz%}</span> </p> </td> 
   <td colname="col2"> <p>Returns current timestamp in JavaScript (ISO 8601) format. </p> </td> 
  </tr> 
 </tbody> 
</table>

