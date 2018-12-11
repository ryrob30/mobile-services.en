---
description: This information helps you work with App Transport Security (ATS), which is a new set of security requirements for iOS 9.
seo-description: This information helps you work with App Transport Security (ATS), which is a new set of security requirements for iOS 9.
seo-title: App Transport Security
solution: Marketing Cloud,Analytics
title: App Transport Security
topic: Developer and implementation
uuid: e9ee13cf-9802-492e-8b11-95f028e34e61
index: y
internal: n
snippet: y
---

# App Transport Security{#app-transport-security}

This information helps you work with App Transport Security (ATS), which is a new set of security requirements for iOS 9.

Starting with iOS 9, Apple introduced [App Transport Security](https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/), a set of requirements that conforms to best practices for secure connections. For the Adobe Mobile SDK version 4.7 or later to work seamlessly with ATS, use the enable SSL option in the [!DNL Manage App Settings] page. For more information, see [Manage App Settings](https://marketing.adobe.com/resources/help/en_US/mobile/c_manage_app_settings.html) or [ADBMobile JSON Config](../configuration/json-config/json-config.md#concept_105FBD9EBABE4B21BD7D49687AB2D5BA).

In [!DNL Adobe Mobile Services], by selecting the **[!UICONTROL Use HTTPS]** option in the [!DNL Manage App Settings] page, all hits from [!DNL Analytics], [!DNL Audience Manager], [!DNL Target], and [!DNL Experience Cloud ID services] are sent via HTTPS.

As an alternative, you can also choose to whitelist service the following servers: 

<table id="table_BD4CB2193C5D4971B5E5008964EFD7ED"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Product </th> 
   <th colname="col2" class="entry"> Instructions </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Analytics </td> 
   <td colname="col2"> <p>To whitelist your <span class="keyword"> Analytics</span> server, add your tracking server domain to your <span class="filepath"> info.plist</span> file as an exception domain for ATS. </p> <p>The tracking server domain can be found in the <span class="uicontrol"> Analytics</span> section of the <span class="filepath"> ADBMobileConfig.json</span> file or in the <span class="uicontrol"> Analytics</span> section in the <span class="wintitle"> Manage App Settings</span> page. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Audience Manager </td> 
   <td colname="col2"> <p>Your <span class="keyword"> Audience Manager</span> domain is found in the server property of the <span class="filepath"> audienceManager</span> object in your <span class="filepath"> ADBMobileConfig.json</span> file. </p> <p>If you are using <span class="keyword"> Audience Manager</span> in your app, and SSL is not enabled, add this server as an exception domain for ATS in your <span class="filepath"> Info.plist</span> file </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Target </td> 
   <td colname="col2"> <p>You can add your <span class="keyword"> Target</span> endpoint to your <span class="filepath"> Info.plist</span> file as an exception domain for ATS. </p> <p>To find your <span class="keyword"> Target</span> endpoint, find the <span class="filepath"> clientCodeproperty</span> in the target object of your <span class="filepath"> ADBMobileConfig.json</span> file. Your endpoint will be <span class="filepath"> https://{clientCode}.tt.omtrdc.net</span>. </p> <p>For example, if your <span class="filepath"> clientCodeproperty</span> is “myCompany”, your endpoint will be <span class="filepath"> https://myCompany.tt.omtrdc.net</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Experience Cloud ID service </td> 
   <td colname="col2"> <p>You can add the <span class="keyword"> Experience Cloud</span> server as an exception domain for ATS in your <span class="filepath"> Info.plist</span> file. This domain is <span class="filepath"> dpm.demdex.net</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile Services: Acquisition </td> 
   <td colname="col2"> <p>Whitelist the Acquisition server as an exception domain for ATS in your <span class="filepath"> Info.plist </span>file. This domain is <span class="filepath"> c00.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile Services: In-App Messages </td> 
   <td colname="col2"> <p>If you are using in-app messages, you might need to add entries into the exception domain for ATS for each URL you use that is not HTTPS. This list includes hosted images and any URL embedded into your custom full screen message HTML. </p> <p>For more detail on setting up exceptions domain in a <span class="filepath"> info.plist</span> file, see the Exceptions section on Apple’s <a href="https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/" format="https" scope="external"> App Transport Security Technote</a> page. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!TIP]
>
>These considerations affect the connections that are made by the Adobe Mobile SDK and do not impact web view or other connections that are made by your app.

