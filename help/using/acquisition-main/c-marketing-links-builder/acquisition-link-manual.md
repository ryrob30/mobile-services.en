---
description: You can create marketing links to acquire new mobile app users on-the-fly by manually configuring the URL parameters.
keywords: mobile
seo-description: You can create marketing links to acquire new mobile app users on-the-fly by manually configuring the URL parameters.
seo-title: Create Acquisition Link Manually
solution: Marketing Cloud,Analytics
title: Create Acquisition Link Manually
topic: Metrics
uuid: d7709203-f793-4982-adaa-9c3c914aca2b
index: y
internal: n
snippet: y
---

# Create Acquisition Link Manually{#create-acquisition-link-manually}

You can create marketing links to acquire new mobile app users on-the-fly by manually configuring the URL parameters.

>[!IMPORTANT]
>
>This feature requires SDK version 4.6 or later. For more information, see [Acquisition Prerequisites](../../acquisition-main/c-acquisition-prerequisites.md#concept_1395BCF2199642E7B653928E1A15AD19).

The following diagram illustrates the components of a manually built tracking link and displays the different URL parameters that you must configure properly when manually creating acquisition links.

![](assets/acquisition_url.png)

This link is configured to perform a platform-specific redirect to the Google Play store or the Apple App Store for a mobile app. If the destination cannot be determined, the default store has been set to the Apple App Store. After the app has been installed, the `my.custom.key:test` custom context key is attached to the Analytics Install Hit.

To manually create links, use the following URL format:

[!DNL http(s)://c00.adobe.com/v3/ {mobile-services-app-hash}/start? {parameters}]

For iOS, ensure that you use the correct protocol:

>[!TIP]
>
>The version of Android SDK you are using has no impact on this process.

* Use **HTTP** if you are using the iOS SDK older than version 4.7.0, or if you are using iOS SDK 4.7.0 or later *and* **[!UICONTROL Use HTTPS]** is **not** selected on the [!DNL Manage App Settings] page. 
* Use **HTTPS** if you are using iOS SDK 4.7.0 or later and **[!UICONTROL Use HTTPS]** **is** selected on the [!DNL Manage App Settings] page

Where the following conditions have been met:

* `{mobile-services-app-hash}` matches the application identifier in the configuration file [!DNL (acquisition:appid]).

  You can locate `{mobile-services-app-has}` in the [!DNL Manage App Settings] page under [!DNL Acquisition SDK Options] in the [!DNL Tracking ID] field.

  ![](assets/tracking-id.png)

* [!DNL {parameters}] is a list of standard specifically named URL query parameters

Here is the list of parameters:  

<table id="table_2C4F195B8271476885DFA226C81051B6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> URL Parameter </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Example Value </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td> <p>a_g_id </p> </td> 
   <td> <p>Google Play Store App Identifier </p> </td> 
   <td> <p>com.adobe.beardcons </p> </td> 
  </tr> 
  <tr> 
   <td> <p>a_g_lo </p> </td> 
   <td> <p>Google Play Store Locale Override </p> </td> 
   <td> <p>ko </p> </td> 
  </tr> 
  <tr> 
   <td> <p>a_i_id </p> </td> 
   <td> <p>iTunes App Identifier </p> </td> 
   <td> <p>835196493 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>a_i_lo </p> </td> 
   <td> <p>iTunes Locale Override </p> </td> 
   <td> <p>jp </p> </td> 
  </tr> 
  <tr> 
   <td> <p>a_dd </p> </td> 
   <td> <p>Default Store for Auto Redirect </p> </td> 
   <td> <p>i | g </p> </td> 
  </tr> 
  <tr> 
   <td> <p>a_cid </p> </td> 
   <td> <p>Custom ID Override (generally IDFA for iOS or ADID for Android) </p> </td> 
   <td> <p>Any String &lt; 255 characters (UTF-8 encoded) </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ctx* </p> </td> 
   <td> <p>Keys prefixed with ctx will end up in Context Data of the resulting launch hit </p> </td> 
   <td> <p>ctxmy.custom.key=myValue </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ctxa.referrer.campaign.name </p> </td> 
   <td> <p>Acquisition Campaign Name </p> <p>This parameter is required for reporting if you want to compare the performance of different acquisition links. </p> </td> 
   <td> <p>2015 Summit Conference </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ctxa.referrer.campaign.trackingcode </p> </td> 
   <td> <p>Tracking Code </p> <p>This parameter is required for reporting if you want to compare the performance of different acquisition links. </p> </td> 
   <td> <p>lexsxouj </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ctxa.referrer.campaign.source </p> </td> 
   <td> <p>Source </p> </td> 
   <td> <p>Ad Network </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ctxa.referrer.campaign.medium </p> </td> 
   <td> <p>Medium </p> </td> 
   <td> <p>Email </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ctxa.referrer.campaign.content </p> </td> 
   <td> <p>Content </p> </td> 
   <td> <p>Image # 325689 </p> </td> 
  </tr> 
  <tr> 
   <td> <p>ctxa.referrer.campaign.term </p> </td> 
   <td> <p>Term </p> </td> 
   <td> <p>hiking+boots </p> </td> 
  </tr> 
 </tbody> 
</table>

Remember the following information when you manually create acquisition links:

* All parameters that do not match parameters in the table are passed on as part of the app store redirect. 
* All parameters are technically optional, although the link will be nonfunctional if at least one store ID is specified.

  An example of a store ID is `a_g_id`/ `a_i_id`. 

* If the destination store cannot be automatically determined, and no default is provided, an 404 error is returned.

