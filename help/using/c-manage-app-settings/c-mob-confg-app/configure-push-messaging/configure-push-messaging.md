---
description: You can use this information to help you configure the Push Services options on the Manage App Settings page while creating a new app or editing an existing app.
keywords: mobile
seo-description: You can use this information to help you configure the Push Services options on the Manage App Settings page while creating a new app or editing an existing app.
seo-title: Configure Push Messaging
solution: Marketing Cloud,Analytics
title: Configure Push Messaging
topic: Metrics
uuid: 6763858d-6046-4d36-87c0-cf3600a44fb1
index: y
internal: n
snippet: y
---

# Configure Push Messaging{#configure-push-messaging}

You can use this information to help you configure the Push Services options on the Manage App Settings page while creating a new app or editing an existing app.

<a id="section_BBF96ABD214C4BFF813FA993E0E5170F"></a>

Before you configure push messaging, review the following information:

* You must perform several prerequisite tasks. For more information about these tasks, see [Prerequisites to Enable Push Messaging](../../../c-manage-app-settings/c-mob-confg-app/configure-push-messaging/prerequisites-push-messaging.md#concept_28A61FEE3C7F48F1866BD1995EC43ACE). 
* **Report Suite Considerations** You can configure one app store app for Apple and one for Google in each report suite. If you need additional apps, for example, one for a production environment and one for a dev environment, set up a new app store app and a new report suite for each environment.

>[!IMPORTANT]
>
>Moving your app to a new report suite is not supported. If you migrate to a new report suite, your push configuration can break, and messages might not be sent.

<a id="section_DE56AD8E81D544FDAD934D1B88A0EA54"></a>

1. Type information in the following fields under **[!UICONTROL Push Services]**:

<table id="table_AC63B06E90384C408149E34AE6D2A44F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Apple </span> </p> </td> 
   <td colname="col2"> <p><b>Private Key</b> </p> <p>Browse to and select your valid private key (<span class="filepath"> .p12</span>, <span class="filepath"> .key</span>, or <span class="filepath"> .pen</span>). </p> <p> <p>Important: If the file you select for the <span class="uicontrol"> Private Key</span> input also contains a certificate, you do not need to specify the certificate. </p> </p> <p><b>Certificate</b> </p> <p>Specify a valid certificate. This option is required only when the <span class="uicontrol"> Private Key</span> input does <b>not</b> contain a certificate. </p> <p>For more information about obtaining the SSL certificate and private key, see <a href="../../../c-manage-app-settings/c-mob-confg-app/configure-push-messaging/configure-app-apns-gcm.md#concept_AEF9A450381641228954594B864C0B1B" format="dita" scope="local"> Configure App to use APNS or GCM</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Google </span> </p> </td> 
   <td colname="col2"> <p><b>API Key</b> </p> <p>Specify a valid API key. </p> <p>For more information about obtaining the API key, see <a href="../../../c-manage-app-settings/c-mob-confg-app/configure-push-messaging/configure-app-apns-gcm.md#concept_AEF9A450381641228954594B864C0B1B" format="dita" scope="local"> Configure App to use APNS or GCM</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

   For more information, see the following topics:

    * **Android: ** [Push Messaging](https://marketing.adobe.com/resources/help/en_US/mobile/android/push_messaging.html) in the Android SDK 4.x for Experience Cloud Solutions guide. 
    
    * **iOS: ** [Push Messaging](https://marketing.adobe.com/resources/help/en_US/mobile/ios/push_messaging.html) in the iOS SDK 4.x for Experience Cloud Solutions guide.

1. Click **[!UICONTROL Save]**.

