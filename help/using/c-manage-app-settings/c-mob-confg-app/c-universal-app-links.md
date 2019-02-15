---
description: Starting in iOS 9.2, deep linking is no longer supported. You must use Universal Links (iOS) and App Links (Android) for deep linking into your app or website.
keywords: mobile
seo-description: Starting in iOS 9.2, deep linking is no longer supported. You must use Universal Links (iOS) and App Links (Android) for deep linking into your app or website.
seo-title: Universal Links and App Links
solution: Marketing Cloud,Analytics
title: Universal Links and App Links
topic: Metrics
uuid: 8d6441dc-4307-4454-95ea-d77ec796f918
---

# Universal Links and App Links{#universal-links-and-app-links}

Starting in iOS 9.2, deep linking is no longer supported. You must use Universal Links (iOS) and App Links (Android) for deep linking into your app or website.

## Universal Links and App Links {#section_F8147944679A42E59CF4FD8814E5EF12}

A Universal Link is a link that can be handled by an iOS application or the browser and is known as deeplinking. Starting with iOS 9.2, deeplinking is no longer supported. For more information about Universal Links, see [Support Universal Links](https://developer.apple.com/library/content/documentation/General/Conceptual/AppSearch/UniversalLinks.html).

An App Link is the Android version of the Universal Link. Although deeplinking might currently still work on all Android operating systems, Adobe Mobile Services supports App Links because a marketing link should be consistent across all platforms. For more information about App Links, see the [Handling Android App Links](https://developer.android.com/training/app-links/index.html).

## Setting up site-association documents in Adobe Mobile Services {#section_A9589564AF784643B376F6791222F778}

1. In the Mobile Services home page, select the app for which you want to set up Universal Links or App Links. 
1. Click **[!UICONTROL Manage App Settings]**. 
1. Ensure the iOS or Android app that handles UL/AL is added to the **[!UICONTROL Add App Store Apps]** section.

   >[!TIP]
   >
   >If this section does not display, click the **[!UICONTROL Add App Store App]** link.

1. Scroll to **[!UICONTROL Universal Links and App Links Options]** at the bottom of the [!DNL App Information] page. 

1. Complete one of the following tasks:

    * For iOS, select an iOS app and type the App ID. 
    * For Android, select an Android app and type a SHA-256 certificate fingerprint.

1. Click **[!UICONTROL Save]**.

   You must provide at least the iOS App ID or one Android App selection and SHA-256 certificate or you will receive an error.

>[!IMPORTANT]
>
>You can update the documents by clicking **[!UICONTROL Update]** from the **[!UICONTROL Universal Links and App Links Options]** section. However, when you click **[!UICONTROL Update]**, a warning notifies you that all Universal Links / App Links you have created in the past will be affected.

## Create a Universal / App Link {#section_609ADEFFB9B441C4A8C45E936D0DC859}

For more information, see [Create or Edit Marketing Links](/help/using/acquisition-main/c-marketing-links-builder/t-create-edit-adobe-links/t-create-edit-adobe-links.md).

1. Select the app from the Mobile Services home page, expand **[!UICONTROL Acquisition]**, and click **[!UICONTROL Marketing Link Builder]**. 
1. Click **[!UICONTROL Create New]**. 
1. Under **[!UICONTROL Marketing Link Options]**, select **[!UICONTROL Use Universal Links or App Links]**.

   If you configured the site-association documents from the steps above, this option is selected by default. If not, **[!UICONTROL Use Universal Links or App Links]** is disabled and **[!UICONTROL Use Interstitials]** is selected by default.

   If **[!UICONTROL Use Universal Links or App Links]** is selected, an additional field titled **[!UICONTROL Custom Path]** is displayed. This allows users to define the URL path after the domain with any query parameter. For example, if you type `my/universal/link?os=9.2`, your full marketing link URL becomes `https://[marketing link domain]/my/universal/link?[AMS default query parameters]&os=9.2`. 

1. Click the **[!UICONTROL Decisions]** tab. 
1. Configure your decision tree.

   If the iOS or Android app is installed, the app will handle the deeplink with its logic, and the final destination serves only as the fallback case. (The app is not installed.) Therefore, it can only be a web link or store link. 

1. Click **[!UICONTROL Save]**.

>[!TIP]
>
>Once a marketing link is saved, the **[!UICONTROL Marketing Links Options]** cannot be altered. This is because you do not want to change the behavior of the marketing links that may have already been distributed.

