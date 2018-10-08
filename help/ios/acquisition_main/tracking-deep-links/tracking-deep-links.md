---
description: You can use this information to track deep and deferred deep links in your mobile apps by using the Adobe Mobile iOS SDK.
seo-description: You can use this information to track deep and deferred deep links in your mobile apps by using the Adobe Mobile iOS SDK.
seo-title: Tracking Deep Links
solution: Marketing Cloud,Analytics
title: Tracking Deep Links
uuid: 5dfdadaa-cc30-4d96-b364-ce9f8c422bd9
index: y
internal: n
snippet: y
translate: y
---

# Tracking Deep Links

You can use this information to track deep and deferred deep links in your mobile apps by using the Adobe Mobile iOS SDK.

For more information about how marketers use deep linking in their applications, see [Acquisition](https://marketing.adobe.com/resources/help/en_US/mobile/index.html?f=acquisition_main) in the [!DNL Adobe Mobile Services] documentation.

This section contains the following information:

* [Getting Started](../../acquisition_main/tracking-deep-links/tracking-deep-links.md#section_29495797A02E48C49CE7A2E3AE170ABD) 
* [Deep Link Public Info](../../acquisition_main/tracking-deep-links/tracking-deep-links.md#section_44600E9AA68D4A53AA0C14BD86CC5284)

## Getting Started {#section_29495797A02E48C49CE7A2E3AE170ABD}

**Tracking Deep Links**

1. Add the SDK to your project and implement Lifecycle metrics.

   For more information, see [Core Implementation and Lifecycle](../../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972). 
1. Register the application to handle [Inter-App Communications](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/Inter-AppCommunication/Inter-AppCommunication.html#//apple_ref/doc/uid/TP40007072-CH6-SW10) or [Support Universal Links](https://developer.apple.com/library/ios/documentation/General/Conceptual/AppSearch/UniversalLinks.html). 

1. Track deep link in openURL.

   Here is a sample track deep link:

   ```
   - (BOOL)application:(UIApplication *)application handleOpenURL:(NSURL *)url { 
       [ADBMobile trackAdobeDeepLink:url]; 
       /* 
        Handle deep link 
        */ 
     
       return YES; 
   } 
     
   - (BOOL)application:(UIApplication *)app openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options { 
       [ADBMobile trackAdobeDeepLink:url]; 
       /* 
        Handle deep link 
        */ 
     
       return YES; 
   }
   ```

The [!DNL Adobe Mobile] SDK can parse key and value pairs of data appended to any deep or universal link, provided that the link contains a key with a `a.deeplink.id` label and a corresponding non-null and user generated value. All key and value pairs of data that are appended to the link will be parsed, attached to a lifecycle hit, and sent to [!DNL Adobe Analytics], provided the link contains the `a.deeplink.id` key and value.

Additionally, you might also choose to append one or more of the following reserved keys (with user-generated values) to the deep or universal link:

* `a.launch.campaign.trackingcode` 
* `a.launch.campaign.source` 
* `a.launch.campaign.medium` 
* `a.launch.campaign.term` 
* `a.launch.campaign.content`

These keys are pre-mapped variables for reporting in [!DNL Adobe Analytics]. For more information on mapping and processing rules, see [Processing Rules and Context Data](../../getting_started/proc_rules.md#concept_4DAF0756D0DB43BD8C0627E023665FA5).

**Tracking Deferred Deep Links**

1. Register Adobe data callback.

   ```
   [ADBMobile registerAdobeDataCallback:^(ADBMobileDataEvent event, NSDictionary * _Nullable adobeData) { 
   }];
   ```

1. Handle `ADBMobileDataEventDeepLink` within `AdobeDataCallback`.

   ```
   [ADBMobile registerAdobeDataCallback:^(ADBMobileDataEvent event, NSDictionary * _Nullable adobeData) { 
       if (event == ADBMobileDataEventDeepLink) { 
           [self handleDeepLink:adobeData[ADBConfigKeyCallbackDeepLink]]; 
       } 
   }];
   ```

## Deep Link Public Information {#section_44600E9AA68D4A53AA0C14BD86CC5284}

**Methods**

```
/** 
 * @brief Tracks a Adobe Deep Link click-through 
 * @param url The URL resource received from UIApplication delegate method. 
 * @note Adobe Link data will be appended to the lifecycle call if it is a launch event, otherwise an extra call will be sent. 
 */ 
+ (void) trackAdobeDeepLink:(nullable NSURL *)url;
```

**Constants**

```
/* 
 * Used within ADBMobileDataCallback 
 * Key for deep link URL. 
 */ 
FOUNDATION_EXPORT NSString *const __nonnull ADBConfigKeyCallbackDeepLink;
```

