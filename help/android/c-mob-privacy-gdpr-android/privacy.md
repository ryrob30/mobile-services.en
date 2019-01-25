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

* **Opt in**

  * **Analytics**: Hits are sent.  
  * **Target**: Mbox requests are sent. 
  * **Audience Manager**: Signals and ID syncs are sent. 
  * Value in the JSON Config file: `optedin`
  * Value in `setPrivacyStatus`: `MOBILE_PRIVACY_STATUS_OPT_IN`

* **Opt out**

  * **Analytics**: Hits are discarded. 
  * **Target**: Mbox requests are not allowed. 
  * **Audience Manager**: Signals and ID syncs are not allowed.
  * Value in the JSON config file: `optedout`
  * Value in `setPrivacyStatus`: `MOBILE_PRIVACY_STATUS_OPT_OUT`

* **Unknown**

  * **Analytics**: If offline tracking **enabled**, hits are saved until the privacy status changes to opt-in (hits are sent) or opt-out (hits are discarded).
  
    If offline tracking <b>is not</b> enabled, hits are discarded until the privacy status changes to opt-in. 
  * **Target**: Mbox requests are sent. 
  * **Audience Manager**: Signals and ID syncs are sent. 
  * Value in the JSON config file: `optunknown`
  * Value in `setPrivacyStatus`: `MOBILE_PRIVACY_STATUS_UNKNOWN`

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

