---
description: You can configure your app to use Apple Push Notification Service (APNS) or Google Cloud Messaging (GCM).
keywords: mobile
seo-description: You can configure your app to use Apple Push Notification Service (APNS) or Google Cloud Messaging (GCM).
seo-title: Configure App to use APNS or GCM
solution: Marketing Cloud,Analytics
title: Configure App to use APNS or GCM
topic: Metrics
uuid: fa411f2a-ba47-4499-bbe5-1aedef6b49ad
---

# Configure your app to use APNS or GCM{#configure-app-to-use-apns-or-gcm}

You can configure your app to use Apple Push Notification Service (APNS) or Google Cloud Messaging (GCM).

## Android Apps {#section_41D304102CDF4586911EC1413AD35A10}

**[!UICONTROL If GCM is not enabled in your app]**

To configure your Android app to use GCM, if GCM is not enabled in your app:

1. Go to [https://developers.google.com/mobile/add](https://developers.google.com/mobile/add) and log in with your [Google Dev credentials](https://developers.google.com/mobile/add). 

1. Click **[!UICONTROL Pick a Platform]** and select **[!UICONTROL Android App]**. 
1. Select the app and the app package name. 
1. Complete the process to enable Google services for your Android app. 
1. Click **[!UICONTROL Choose and Configure Services]**. 
1. Add Cloud Messaging by clicking the **[!UICONTROL +]** button on its icon. 
1. Click **[!UICONTROL Generate Configuration Files]**. 
1. Copy the **[!UICONTROL Server API key]** and **[!UICONTROL Sender ID]** for later use.

   For example:

   ```
    - API Key = AIzaSyC6FNgsCOpBL5eXhDvwf8979mWba6x7Roo
   ```

   ```
   - Sender ID = 835015092250
   ```

**[!UICONTROL If GCM is enabled in your app]**

To configure your Android app to use GCM (Google Cloud Messaging) when GCM is enabled in your app:

1. Go to [https://console.developers.google.com/project](https://console.developers.google.com/project). 
1. Select your app that is GCM enabled. 
1. Note the **[!UICONTROL Project number]** in the **[!UICONTROL Overview]** section. 

   This is the GCM Sender ID for the app.

   For example:

   ```
   - Project Number = 835015092250
   ```

1. Under the **[!UICONTROL APIs & Auth]** header, select **[!UICONTROL Credentials]**. 
1. Copy the API Key under the **[!UICONTROL Public API access]** section for use later.

   For example:

   ```
    - API Key = AIzaSyC6FNgsCOpBL5eXhDvwf8979mWba6x7Roo
   ```

## iOS Apps {#section_2031DAB485FC4D2B9027E42AD90B294D}

To configure your iOS app to use APNS:

1. Go to [https://developer.apple.com/account](https://developer.apple.com/account) and log in to your [Apple Developer account](https://developer.apple.com/account). 
1. Under **[!UICONTROL iOS Apps]**, select **[!UICONTROL Identifiers]**. 
1. If you already have an App ID set up for push, skip to Step 11. 
1. Press the **[!UICONTROL +]** button to create a new App ID. 
1. Type an App ID Description. 
1. Type an App ID Suffix.

   >[!IMPORTANT]
   >
   >To support push, you must use an Explicit App ID that does **not** use a wild card (for example, `- com.tester.pushSample`).

1. Under **[!UICONTROL App Services]**, select the **[!UICONTROL Push Notifications]** check box. 
1. Click **[!UICONTROL Continue]**. 
1. Click **[!UICONTROL Submit]**. 
1. Click **[!UICONTROL Done]**. 
1. Select your App ID that is set up to use push messaging from the list and click **[!UICONTROL Edit]**. 
1. If you already have a Push Certificate created, skip to Step 15. 
1. Scroll down to **[!UICONTROL Push Notifications]** and click the correct **[!UICONTROL Create Certificate...]** button.

   The button you click depends whether you are creating a certificate for Development or Production. 
1. Follow the steps outlined on the Apple website to create your CSR, upload it, and generate your certificate. 
1. Scroll down to the **[!UICONTROL Push Notifications]** section and download the SSL certificate you just created. 
1. Double-click the certificate you downloaded to add it to your keychain.

**SSL Certificate and Private Key**

To get your SSL Certificate and Private Key (APNS):

1. Open **[!UICONTROL Keychain Access]**. 
1. Click **[!UICONTROL My Certificates]** and find the appropriate **[!UICONTROL Push iOS Push Services Certificate]** for your app and environment.

   You can identify the correct certificate by matching the bundle ID and whether it is Development or Production. 

1. Expand the certificate and verify that it contains a private key. 
1. Right-click the private key and select **[!UICONTROL  Export " *`<name of key>`*]**. 
1. Go through the dialog and save your new [!DNL .p12] file.

   You do not have to type a password. 

1. In the **[!UICONTROL Private Key]**, type the [!DNL .p12] file.

