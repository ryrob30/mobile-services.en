---
description: You can use the iOS extension helps you collect usage data from your Apple Watch Apps (WatchOS 1), Today Widgets, Photo Editing widgets, and other iOS extension apps.
seo-description: You can use the iOS extension helps you collect usage data from your Apple Watch Apps (WatchOS 1), Today Widgets, Photo Editing widgets, and other iOS extension apps.
seo-title: iOS Extension Implementation
solution: Marketing Cloud,Analytics
title: iOS Extension Implementation
topic: Developer and implementation
uuid: 8afc03fe-403e-4643-ada1-30e403ede238
---

# iOS Extension Implementation{#ios-extension-implementation}

You can use the iOS extension helps you collect usage data from your Apple Watch Apps (WatchOS 1), Today Widgets, Photo Editing widgets, and other iOS extension apps.

This section contains the following information:

* [Recommendations for Using the iOS SDK Instead of Your Own...](../ios-ext/ios-ext.md#section_97577331FD9E4FFBBE05D402C67AEE69) 
* [Getting Started](../ios-ext/ios-ext.md#section_D0BE4F780C9C4CD8ADD2AD4EE0BD5FD4) 
* [Additional Notes](../ios-ext/ios-ext.md#section_21497E81231549CB9F164DEECFF5BA0D)

## Recommendations for Using the iOS SDK Instead of Your Wrapper {#section_97577331FD9E4FFBBE05D402C67AEE69}

>[!IMPORTANT]
>
>We strongly recommend that you use the iOS SDK rather than using your wrapper.

Apple provides a set of APIs that lets the Watch app communicate with the containing app by sending requests to the containing app and receiving the responses. Although you can send tracking data as a dictionary from the Watch app to the containing app and call any tracking method on the containing app to send the data, this solution has limitations.

In most cases when a user is using the Watch app, the containing app is running in the background, and it is only safe to call `TrackActionInBackground`, `TrackLocation`, and `TrackBeacon`. Calling other tracking methods interferes with lifecycle data, so you should use only these three methods to send the data from Watch app.

Even if these three tracking methods meet your requirements, use the iOS SDK, because the SDK for the Watch app includes all [!DNL Mobile] features except in-app messaging.

## Getting Started {#section_D0BE4F780C9C4CD8ADD2AD4EE0BD5FD4}

>[!NOTE] {othertype="Prerequisite"}
>
>Ensure that you have a project with at least the following targets: 
>
>* One target to contain the app. 
>* One target for the extension. 
>

If you are working on a WatchKit app, you should have a third target. For more information on developing for Apple Watch, see [Developing for Apple Watch](https://developer.apple.com/library/ios/documentation/General/Conceptual/WatchKitProgrammingGuide/index.html#//apple_ref/doc/uid/TP40014969-CH8-SW1) in the *Apple Watch Programming Guide.*

## Configuring the Containing App {#section_0BAB0842E4C04A62B5E03DFC4BA77851}

Complete the following steps in your Xcode project:

1. Drag the [!DNL AdobeMobileLibrary] folder into your project. 
1. Ensure that [!DNL ADBMobileConfig.json] is a member of the containing app's target. 
1. On the **[!UICONTROL Build Phases]** tab of your containing app's target, expand the **[!UICONTROL Link Binary with Libraries]** section and add the following libraries:

    * `AdobeMobileLibrary.a` 
    * `libsqlite3.dylib` 
    * `SystemConfiguration.framework`

1. Open the **[!UICONTROL Capabilities]** tab of the containing app's target, enable **[!UICONTROL App Groups]**, and add a new app group (for example, [!DNL group.com.adobe.testApp]). 

1. In your application delegate, set the app group in [!DNL application:didFinishLaunchingWithOptions] before making any interactions with the Adobe Mobile library:

   ```
   [ADBMobile 
         setAppGroup:@"group.com.adobe.testApp"];
   ```

1. Confirm that your app builds without unexpected errors.

## Configuring the Extension {#section_28C994B7892340AC8D1F07AF26FF3946}

1. Ensure that [!DNL ADBMobileConfig.json] is a member of the extension's target. 
1. On the **[!UICONTROL Build Phases]** tab of your extension’s target, expand the **[!UICONTROL Link Binary with Libraries]** section and add the following libraries:

    * `AdobeMobileLibrary_Extension.a` 
    * `libsqlite3.dylib` 
    * `SystemConfiguration.framework`

1. Open the **[!UICONTROL Capabilities]** tab of the extension's target, enable **[!UICONTROL App Groups]**, and select the app group that you added in step 4 of *Configuring the Containing App* above. 

1. In your [!DNL InterfaceController], set the app group in [!DNL awakeWithContext:] before making any other interactions with the Adobe Mobile library:

   ```
   [ADBMobile 
         setAppGroup:@"group.com.adobe.testApp"];
   ```

1. Confirm that your app builds without unexpected errors.

## Additional Notes {#section_21497E81231549CB9F164DEECFF5BA0D}

Here is some information to remember:

* An additional context data value, [!DNL a.RunMode] has been added to indicate whether the data comes from your containing app or your extension:

    * [!DNL a.RunMode = Application] This value means that the hit came from the containing app. 
    
    * [!DNL a.RunMode = Extension] This value means that the hit came from the extension.

* If you upgrade from a older version of the SDK, when the containing app is launched, Adobe automatically migrates all the user defaults and cached files from the containing app's folder to the app group's shared folder. 
* If the containing app is never launched, hits from the extension are discarded. 
* The version number and build number must be the same between your containing app and the extension app. 
* No lifecycle call is triggered on iOS extension apps.

