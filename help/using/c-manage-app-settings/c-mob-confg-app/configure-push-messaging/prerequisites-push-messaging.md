---
description: You must complete these tasks before configuring Push Messaging in applications.
keywords: mobile
seo-description: You must complete these tasks before configuring Push Messaging in applications.
seo-title: Prerequisites to Enable Push Messaging
solution: Marketing Cloud,Analytics
title: Prerequisites to Enable Push Messaging
topic: Metrics
uuid: 194e6e07-b794-4152-a838-a4125c3292d4
---

# Prerequisites to Enable Push Messaging {#prerequisites-to-enable-push-messaging}

You must complete these tasks before configuring Push Messaging in applications.

#### Enable the Experience Cloud for Your Company

Your [!UICONTROL] Adobe Analytics Company must be [!UICONTROL] Experience Cloud enabled. You can verify this with your Adobe account executive.

#### Install and Configure the Mobile SDK

* **Install the Mobile SDK**
    The Push Messaging feature requires that you download and install the appropriate 4.6 (or later) Mobile SDK.

    For more information, see [Download the SDKs.](../../../c-manage-app-settings/c-mob-confg-app/t-config-analytics/download-sdk.md)

* **Configure Push Services**

    You must configure push services in the Mobile SDK.

    For more information, see the following content:

    *   [Android: Push Messaging](/help/android/messaging-main/push-messaging/push-messaging.md)
    *   [iOS: Push Messaging](/help/ios/messaging-main/push-messaging/push-messaging.md)

#### Log in to the Mobile Core Service using your Adobe ID

>[!IMPORTANT]
>
>To use the Push Services functionality users must log in to the Mobile Core Service by using their [!DNL Adobe ID] and their Analytics account must be linked to their [!DNL Adobe ID]s. Push Services functionality is not available if users log in using their existing Adobe Analytics accounts.

If users do not have Adobe IDs, complete the following steps:

1. **Experience Cloud Administrator** invites users to the Experience Cloud.

1. **Users** create a personal [!DNL Adobe ID] using the instructions received from the Experience Cloud administrator.
    An email message is automatically sent to each user after the administrator completes the previous step.

1. **Users** log in to Mobile using their [!DNL Adobe ID].

#### Link Users' Accounts in the Experience Cloud

Each user must link the [!UICONTROL] Analytics solution account from the Experience Cloud organization.

1. To sign in to the Experience Cloud with an [!DNL Adobe ID], type [https://marketing.adobe.com](https://marketing.adobe.com) in a browser.

1. In the upper right corner, select the [!UICONTROL] Analytics company name.

1. Click **[UICONTROL Add Organization]** and select **[!UICONTROL Adobe SiteCatalyst/Adobe Social]** from the drop-down list.

1. Type the company name, your legacy credentials for the specified company, and click **[!UICONTROL Link Account]**.

    The [!DNL Adobe ID] is now linked to your [!UICONTROL] Analytics account, company, and log-in credentials.

For more information, see [Troubleshooting Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html).

#### Configure Push Services and the SDK ID service in the Mobile User Interface

Before you enable the ID service for your app, the Push Services section is disabled. But, after you [enable the ID service](../../../c-manage-app-settings/c-mob-confg-app/t-config-visitor.md#task_568C5F05E4E044E9BCCCF91ABBA736F7), the Push Services section is enabled.

>[!IMPORTANT]: You must click **[!UICONTROL Save]** to save your changes and refresh the Push Services.
>
>You can configure one app store app for Apple and one for Google in each report suite. If you need additional apps, for example, one for a production environment and one for a dev environment, set up a new app store app and a new report suite for each environment.

* For **Apple**, drag and drop your private key and/or certificate. If your private key is password-encrypted, type its password.
  * For the **Private Key**, drag and drop your private-key file into the box. You can also click **[!UICONTROL Browse]** to select the file. This file contains the private key. The certificate might also be included in this file (`.p12`, `pkcs12`, `.pfx`, `.key`, `.pem`).
  * For the **Private Key Password**, if your private-key file is encrypted, type the password.
    (Conditional) For the **Certificate**, drag and drop your certificate file into the box. You can also click Browse to select the file.
    This field is not required if the private-key file also contains the certificate ( `.cert`, `.cer`, `.crt`, `.pem`).

* For **Google**, specify the API key for the app.

    Click Test to validate that the app and Mobile Services are configured correctly. This option is useful for debugging and troubleshooting.

    Type the device's push tokens that you want to send the message. You can send the message to multiple devices by specifying tokens in a comma-separated list.

    ![](assets/push_test_list.png)
