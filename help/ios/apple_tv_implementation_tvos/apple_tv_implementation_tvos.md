---
description: This information helps you implement Apple TV with tvOS.
seo-description: This information helps you implement Apple TV with tvOS.
seo-title: Apple TV Implementation with tvOS
solution: Marketing Cloud,Analytics
title: Apple TV Implementation with tvOS
topic: Developer and implementation
uuid: e2e3a901-385e-4643-ba04-45dde6c9406c
index: y
internal: n
snippet: y
translate: y
---

# Apple TV Implementation with tvOS

This information helps you implement Apple TV with tvOS.

With Apple TV, you can now create applications to run in the native tvOS environment. You can create a native app by using several frameworks in iOS, or you can create your app by using XML templates and JavaScript.

>[!TIP]
>
>tvOS suppor is available starting in AdobeMobileLibrary version 4.7.0.

This section contains the following information:

* [Getting Started](../apple_tv_implementation_tvos/apple_tv_implementation_tvos.md#section_CAB40A5B5FC745068C8A5DF8F9AB6199) 
* [Configuring a Native App for tvOS](../apple_tv_implementation_tvos/apple_tv_implementation_tvos.md#section_5095F19B3C4545F68E8C1E37A7E303AE) 
* [Configuring a TVML/TVJS App for tvOS](../apple_tv_implementation_tvos/apple_tv_implementation_tvos.md#section_AB2EC8C326654F3387658EBBD990BB12)

## Getting Started {#section_CAB40A5B5FC745068C8A5DF8F9AB6199}

>[!TIP]
>
>We assume that your project has a target that is an Apple TV app that is targeting tvOS. For more information, see [tvOS](https://developer.apple.com/tvos/documentation/).

## Configuring a Native App for tvOS {#section_5095F19B3C4545F68E8C1E37A7E303AE}

Complete the following steps in your Xcode project:

1. Drag the [!DNL AdobeMobileLibrary] folder into your project. 
1. Ensure that [!DNL ADBMobileConfig.json] is a member of your target. 
1. On the **[!UICONTROL Build Phases]** tab of your tvOS app’s target, expand the **[!UICONTROL Link Binary with Libraries]** section and add the following libraries:

    * [!DNL AdobeMobileLibrary_TV.a] 
    * [!DNL libsqlite3.0.tbd] 
    * [!DNL SystemConfiguration.framework]

For information, see the iOS documentation on [iOS](https://developer.apple.com/ios/resources/).

## Configuring a TVML/TVJS App for tvOS {#section_AB2EC8C326654F3387658EBBD990BB12}

1. Drag the [!DNL AdobeMobileLibrary] folder into your project. 
1. Ensure that [!DNL ADBMobileConfig.json] is a member of your target. 
1. On the **[!UICONTROL Build Phases]** tab of your tvOS app’s target, expand the **[!UICONTROL Link Binary with Libraries]** section and add the following libraries:

    * `AdobeMobileLibrary_TV.a` 
    * [!DNL libsqlite3.0.tbd] 
    * [!DNL SystemConfiguration.framework]

1. In the implementation file of your [!DNL TVApplicationControllerDelegate] class, import the SDK.

   ```
   #import “ADBMobile.h"
   ```

1. In the `application:didFinishLaunchWithOptions:` method of your `TVApplicationControllerDelegate` class, pass your `TVApplicationController` object to the SDK with the `installTVMLHooks:` method.

   The Adobe SDK needs access to your app’s `TVApplicationController` to register itself into the JSContext of your app. This step allows you to call the native methods in the Adobe SDK from your JavaScript files.

   ```
   [ADBMobile installTVMLHooks:appController];
   ```

1. In your JavaScript files, use the `ADBMobile` object to access the native methods of the Adobe SDK.

   For a complete listing of the available methods, see [TVJS Methods](../apple_tv_implementation_tvos/tvjs_methods.md#concept_A875FB3AE8A749D19BB8A74AC446CC0F).

