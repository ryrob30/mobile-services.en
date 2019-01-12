---
description: You can use this information to help you configure the Push Services options on the Manage App Settings page while creating a new app or editing an existing app.
keywords: mobile
seo-description: You can use this information to help you configure the Push Services options on the Manage App Settings page while creating a new app or editing an existing app.
seo-title: Configure Push Messaging
solution: Marketing Cloud,Analytics
title: Configure Push Messaging
topic: Metrics
uuid: 6763858d-6046-4d36-87c0-cf3600a44fb1
---

# Configure Push Messaging{#configure-push-messaging}

You can use this information to help you configure the Push Services options on the Manage App Settings page while creating a new app or editing an existing app.

Before you configure push messaging, review the following information:

* You must perform several prerequisite tasks. 

  For more information about these tasks, see [Prerequisites to Enable Push Messaging](../../../c-manage-app-settings/c-mob-confg-app/configure-push-messaging/prerequisites-push-messaging.md#concept_28A61FEE3C7F48F1866BD1995EC43ACE). 
* **Report Suite Considerations** 

    You can configure one app store app for Apple and one for Google in each report suite. If you need additional apps, for example, one for a production environment and one for a dev environment, set up a new app store app and a new report suite for each environment.

>[!IMPORTANT]
>
>Moving your app to a new report suite is not supported. If you migrate to a new report suite, your push configuration can break, and messages might not be sent.

1. Type information in the following fields under **[!UICONTROL Push Services]**:

    * Apple

      * **[!UICONTROL Private Key]**
        Browse to and select your valid private key `.p12`, `.key`, or `.pen`.

        >[!IMPORTANT]
        >If the file that you select for the **[!UICONTROL Private Key]** input also contains a certificate, you do not need to specify the certificate.

      * **[UICONTROL Certificate]**
       Specify a valid certificate. This option is required only when the **[!UICONTROL Private Key]** input does **not** contain a certificate. For more information about obtaining the SSL certificate and private key, see [Configure App to use APNS or GCM](../../../c-manage-app-settings/c-mob-confg-app/configure-push-messaging/configure-app-apns-gcm.md).

    * Google
      * **[!UICONTROL API Key]**
        Specify a valid API key. For more information about obtaining the API key, see [Configure App to use APNS or GCM](../../../c-manage-app-settings/c-mob-confg-app/configure-push-messaging/configure-app-apns-gcm.md).

    For more information, see the following topics:

     * [Push Messaging](/help/android/messaging-main/push-messaging/push-messaging.md) in the Android SDK 4.x for Experience Cloud Solutions guide.
     * [Push Messaging](/help/ios/messaging-main/push-messaging/push-messaging.md) in the iOS SDK 4.x for Experience Cloud Solutions guide.

1. Click **[!UICONTROL Save]**.
