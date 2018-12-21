---
description: Starting with iOS 10, Apple allows you to create an extension called a stand-alone extension that can be distributed without a containing app. With this extension, you do not need an app group, as there is no containing app with which to share data.
seo-description: Starting with iOS 10, Apple allows you to create an extension called a stand-alone extension that can be distributed without a containing app. With this extension, you do not need an app group, as there is no containing app with which to share data.
seo-title: Stand-Alone Extension Implementation
solution: Marketing Cloud,Analytics
title: Stand-Alone Extension Implementation
topic: Developer and implementation
uuid: 9b47f082-b78f-4611-968d-014c32ede6bc
---

# Stand-Alone Extension Implementation{#stand-alone-extension-implementation}

Starting with iOS 10, Apple allows you to create an extension called a stand-alone extension that can be distributed without a containing app. With this extension, you do not need an app group, as there is no containing app with which to share data.

>[!IMPORTANT]
>
>Mobile SDK version 4.13.0 or above is required to use stand-alone extensions.

This section contains the following information:

* [Configure your stand-alone extension for use with the SDK](../ios-ext/c-stand-alone-extension-implementation.md#section_B7A84603BB9D4B48BB46BE8D3B9E3CF0) 
* [Additional Notes](../ios-ext/c-stand-alone-extension-implementation.md#section_1C9A55E2309A44BF842310F735702B3D)

## Configure your stand-alone extension for use with the SDK {#section_B7A84603BB9D4B48BB46BE8D3B9E3CF0}

To configure your stand-alone extension:

1. Ensure that `ADBMobileConfig.json` is a member of your extension's target. 
1. Link the following libraries and frameworks:

    * `AdobeMobileLibrary_Extension.a` 
    * `libsqlite3.tbd` 
    * `SystemConfiguration.framework`

1. In the main view controller of your extension, set the extension type to `ADBMobileAppExtensionTypeStandAlone` in the SDK before completing any SDK-related activities. 

   ```
   [ADBMobile setAppExtensionType:ADBMobileAppExtensionTypeStandAlone];
   ```

1. Confirm that your app builds without unexpected errors.

## Additional Notes {#section_1C9A55E2309A44BF842310F735702B3D}

Here is some additional information:

* An additional context data value, [!DNL a.RunMode] has been added to indicate whether the data comes from your containing app or your extension:

    * [!DNL a.RunMode = Application] This value means that the hit came from the containing app. 
    
    * [!DNL a.RunMode = Extension] This value means that the hit came from the extension.

* No lifecycle call is triggered on iOS extension apps.

