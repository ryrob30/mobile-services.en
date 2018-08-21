---
description: Here is some information to help you configure the Android extension, which allows you to collect data from your Android Wearable app.
seo-description: Here is some information to help you configure the Android extension, which allows you to collect data from your Android Wearable app.
seo-title: Android Wearables  Additional Notes
solution: Marketing Cloud,Analytics
title: Android Wearables  Additional Notes
topic: Developer and implementation
uuid: cd770986-c953-40d0-8e04-c0bb4bc555ca
index: y
internal: n
snippet: y
translate: y
---

# Android Wearables: Additional Notes


* The Adobe Mobile Android Wearables extension requires Android version 4.4 (KitKat) or above.
* There is one additional context value, [!DNL  A.RunMode], which has been added to indicate whether the data comes from the containing app or the extension. 
    * [!DNL  RunMode = Application] (the hit comes from handheld app)
    * [!DNL  RunMode = Extension] (the hit comes from wearable app)

* The SDK automatically syncs the [!DNL  aid/vid/visitor service id/privacy] status from the handheld app to the wearable app, so do not call [!DNL  setPrivacyStatus/setUserIdentifier/idSync] from the wearable app. 

* [ In-app messages](../messaging_main/messaging/messaging.md#concept_C780209084B94D44A107332C87FE943E), [ Target](../target_main/target.md#concept_CB9A3D33B3404A17AAB44EF5ADE4447D), and [ Audience Manager](../audience_manager/audiencemgmt.md#concept_526A892D2DC744B98782004E9583F014) are disabled for the wearable app.
