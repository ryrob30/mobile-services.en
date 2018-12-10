---
description: This information helps you use in-app messaging in your iOS apps.
seo-description: This information helps you use in-app messaging in your iOS apps.
seo-title: In-App Messaging
solution: Marketing Cloud,Analytics
title: In-App Messaging
topic: Developer and implementation
uuid: 21fa6a94-bb7f-4c78-843b-a50f1974db22
index: y
internal: n
snippet: y
---

# In-App Messaging{#in-app-messaging}

This information helps you use in-app messaging in your iOS apps.

 To use in-app messaging, you **must** have SDK version 4.2 or later.

Some information to remember:

* Messages and the rules that define when messages are displayed are created in Adobe Mobile services. For more information, see [Create an in-app message](https://marketing.adobe.com/resources/help/en_US/mobile/?f=t_in_app_message). 
* The updates described in this section must be made to the SDK to display in-app messages.

  >[!TIP]
  >
  >You can complete these steps even if you do not have any messages defined. After you define messages, they will be delivered dynamically to your app and displayed without an app store update.

This section contains the following information:

* [Enabling In-App Messages](../../messaging-main/messaging/messaging.md#section_79F984271C3B4366B7B04F864F4FF8C2) 
* [Tracking In-App Messages](../../messaging-main/messaging/messaging.md#section_B85CDF6929564AAEA79338B55E5CB1E8) 
* [Local Fallback Image](../../messaging-main/messaging/messaging.md#section_DEACC1CE549B4573B556A44A52409941)

## Enabling In-App Messages {#section_79F984271C3B4366B7B04F864F4FF8C2}

1. Add the [library to your project and implement lifecycle](../../getting-started/dev-qs.md#concept_13176B6E37F547D6935E37125F457972). 
1. Import the library: 

   ```java
   #import "ADBMobile.h"
   ```

1. Verify that `ADBMobileConfig.json` contains the required settings for In-App messaging. 
1. For in-app messages to be updated dynamically on launch, the `remotes` object must be present and properly configured:

   ```js
   “messages”: [ 
       { 
           “messageId”: “de45c43c-37bf-441f-8cbd-cc3ba3469ebe”, 
           “template”: “fullscreen”, 
           “showOffline”: false, 
           “showRule”: “always”, 
           “endDate”: 2524730400, 
           “startDate”: 0, 
           “audiences”: [], 
           “triggers”: [], 
           “payload”: { // contents change depending on template 
               “html”: “<html>html code goes here</html>” 
           }, 
       }, 
       … 
   ] 
   “remotes” : { 
       “analytics.poi”: “https://assets.adobedtm.com/…/yourfile.json”, 
       “messages”: “https://assets.adobedtm.com/…/yourfile.json” 
   }
   ```

   >[!TIP]
   >
   >`messages` or `remotes` is required.

   If these objects are not configured, [download an updated](../../getting-started/requirements.md#section_044C17DF82BC4FD8A3E409C456CE9A46) `ADBMobileConfig.json` from Adobe Mobile services.

## Tracking In-App Messages {#section_B85CDF6929564AAEA79338B55E5CB1E8}

The iOS Mobile Services SDKs track the following metrics for your in-app messages:

* For full screen and alert style in-app messages:

    * **Impressions**: when user triggers an in-app message. 
    * **Click throughs**: when user pushes the **[!UICONTROL Click-through]** button. 
    
    * **Cancels**: when user pushes the **[!UICONTROL Cancel]** button.

* For custom, full screen in-app messages, the HTML content in the message needs to include the correct code to notify the SDK tracking about the following buttons:

    * **Click-through** (redirect) example tracking: `adbinapp://confirm/?url=http://www.yoursite.com` 
    
    * **Cancel** (close) example tracking: `adbinapp://cancel`

* For local (remote) notifications:

    * **Impressions**: when user triggers the notification. 
    * **Opens**: when user opens app from the notification.

  Here is an example about how to include open tracking:

  ```
  - (BOOL) application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions { 
    
    // handle local notification click-throughs for iOS 10 and older 
    NSDictionary *localNotificationDictionary = launchOptions[UIApplicationLaunchOptionsLocalNotificationKey]; 
    if ([localNotificationDictionary isKindOfClass:[NSDictionary class]]) { 
         [ADBMobile trackLocalNotificationClickThrough:localNotificationDictionary]; 
    } 
    
  } 
  - (void) application:(UIApplication *)application didReceiveLocalNotification:(UILocalNotification *)notification { 
     [ADBMobile trackLocalNotificationClickThrough:notification.userInfo]; 
  }
  ```

## Local Fallback Image {#section_DEACC1CE549B4573B556A44A52409941}

When creating a full screen message in Adobe Mobile services, you can optionally specify a fallback image. If your message is unable to retrieve its intended image from the web, the SDK attempts to load the image with the same name from your application bundle. This allows you to display your message in its original form even if the user is offline, or the predetermined image is unreachable.

The fallback image asset name is specified when configuring the message in Adobe Mobile services.

>[!IMPORTANT]
>
>You need to ensure that the specified resource is available.

