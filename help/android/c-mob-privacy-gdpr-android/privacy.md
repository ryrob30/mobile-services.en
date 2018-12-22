---
description: This information helps you with a GDPR data deletion request.
seo-description: This information helps you with a GDPR data deletion request.
seo-title: Setting the User's Opt Status
solution: Marketing Cloud,Analytics
title: Setting the User's Opt Status
topic: Developer and implementation
uuid: f8a3e6be-44dd-494e-9cda-dbbac86d6772
---

# Setting the User's Opt Status{#setting-the-user-s-opt-status}

This information helps you with a GDPR data deletion request.

>[!IMPORTANT]
>
>Starting with Android SDK 4.15 , setting the privacy status to `unknown` holds Audience Manager and Experience Cloud ID hits.

You can control whether the [!DNL Analytics], [!DNL Target], and [!DNL Audience Manager] activity is allowed on a device by using the following settings:

* `privacyDefault` in [ADBMobile JSON Config](../configuration/json-config/json-config.md#concept_0F700EEE71F94B44A0E4000E6C2DA7FB).

  This setting controls the initial setting that persists until it is changed in the code. 

* The `Config.setPrivacyStatus` method.

  After the privacy setting is changed by using this method, this change remains effective until you change it again or when you uninstall and install the app again. For more information about the methods, see [Configuration Methods](../configuration/methods.md#concept_12F12E3E0E434F8CB997AF4027810EBF).

The following table describes each privacy status: 

<table id="table_B97ABE85C501430F8DB41B1CF583266E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Value in JSON Config </th> 
   <th colname="col4" class="entry"> Value in setPrivacyStatus </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Opt in </td> 
   <td colname="col2"> <p> 
     <ul id="ul_70589B90AFF24AC090BAA8C2732F4C99"> 
      <li id="li_7168B5FFBABF4F8AA5EC934C0D57D6D0"> <p><b>Analytics</b>: Hits are sent. </p> </li> 
      <li id="li_0D7821312FEF429C8ECCAFA1B472846E"> <p><b>Target</b>: Mbox requests are sent. </p> </li> 
      <li id="li_99712718798B4F3CB1DB0C05685666E4"> <p><b>Audience Manager</b>: Signals and ID syncs are sent. </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <span class="codeph"> optedin </span> </td> 
   <td colname="col4"> <span class="codeph"> MOBILE_PRIVACY_STATUS_OPT_IN </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opt out </td> 
   <td colname="col2"> <p> 
     <ul id="ul_FF31CF8C59E5433B938310145BEC334D"> 
      <li id="li_0985E79A6F1D452A8C1A8A7D0EFBAF7C"> <p><b>Analytics</b>: Hits are discarded. </p> </li> 
      <li id="li_D8FC6A5947764583B4B05421BACE7643"> <p><b>Target</b>: Mbox requests are not allowed. </p> </li> 
      <li id="li_9ECC586D0AA94C49A4AC81D86E1F3F7E"> <p><b>Audience Manager</b>: Signals and ID syncs are not allowed. </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <span class="codeph"> optedout </span> </td> 
   <td colname="col4"> <span class="codeph"> MOBILE_PRIVACY_STATUS_OPT_OUT </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unknown </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5C453C30B6FF448FBC09DE260FE8CD41"> 
      <li id="li_245FABB96C6E496B8E90E04E3B4D4061"> <p><b>Analytics</b>: If offline tracking <b>is</b> enabled, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded). </p> <p>If offline tracking <b>is not</b> enabled, hits are discarded until the privacy status changes to opt-in. </p> </li> 
      <li id="li_38BF9B90FD904702A57E538BA2B1E255"> <p><b>Target</b>: Mbox requests are sent. </p> </li> 
      <li id="li_3B81727F49E44E3CB4BF7506C5523DD3"> <p><b>Audience Manager</b>: Signals and ID syncs are sent. </p> </li> 
     </ul> </p> </td> 
   <td colname="col3"> <span class="codeph"> optunknown </span> </td> 
   <td colname="col4"> <span class="codeph"> MOBILE_PRIVACY_STATUS_UNKNOWN </span> </td> 
  </tr> 
 </tbody> 
</table>

## Examples {#section_128AC455EE024193B5D4E5A565B53D00}

```java
public void setOptIn(View view) { 
  Config.setPrivacyStatus(MobilePrivacyStatus.MOBILE_PRIVACY_STATUS_OPT_IN); 
 currentStatus = Config.getPrivacyStatus(); 
} 
public void setOptOut(View view) { 
 Config.setPrivacyStatus(MobilePrivacyStatus.MOBILE_PRIVACY_STATUS_OPT_OUT); 
 currentStatus = Config.getPrivacyStatus(); 
} 
public void setOptUnknown(View view) { 
  Config.setPrivacyStatus(MobilePrivacyStatus.MOBILE_PRIVACY_STATUS_UNKNOWN); 
 currentStatus = Config.getPrivacyStatus(); 
}
```

