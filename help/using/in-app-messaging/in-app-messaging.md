---
description: Create, manage, and report on in-app and push messages.
keywords: mobile
seo-description: Create, manage, and report on in-app and push messages.
seo-title: Messaging
solution: Marketing Cloud,Analytics
title: Messaging
topic: Metrics
uuid: e32d3e35-2d09-4ddf-8919-75dc895abcb3
index: y
internal: n
snippet: y
---

# Messaging {#messaging}

Create, manage, and report on in-app and push messages.

This section contains the following information:

* [In-App Messages](../in-app-messaging/in-app-messaging.md#section_8984F4568BC24D32A87429FFCB5184A6) 
* [Push Messages](../in-app-messaging/in-app-messaging.md#section_90555A55BCE7427A90B1577E14BEF51B) 
* [SDK Documentation for iOS and Android](../in-app-messaging/in-app-messaging.md#section_49ACA880BA3D44B7B3AAF95571F2DA96)

## In-App Messages {#section_8984F4568BC24D32A87429FFCB5184A6}

In-app messages are delivered to users in real-time, based on their actions and traits. The messages are triggered from [!DNL Analytics] data already tracked by the SDK.

The following message types are supported:

* Custom and themed 
* Full screen 
* Native alerts 
* Local notifications

Here is how in-app messaging works:

* Requires SDK v4.2 or later. 
* You must specify who has Mobile App Admin rights, which enables access to acquisition links and in-app messages.

  For more information, see [Roles and Permissions](../gs/c-mob-roles-and-permissions.md#concept_B1EC13F686F742D1AD7025C38F60A70D). 
* After a message is approved, the message is published automatically to the application. 
* The SDK presents the message to users when the message parameters, such as traits, trigger, and schedule, are met. 
* Messages can contain custom HTML or an image, using an online URL.

  A backup or alternative image from the app bundle can also be specified for messages that are triggered while offline. 
* Active and completed messages will provide reports on total views, click-through rates, and so on. 
* Templates are available for custom messages, which allows you to easily build your own in-app message.

## Push Messages {#section_90555A55BCE7427A90B1577E14BEF51B}

Push messages are sent to users who have opted in to receive notifications. You can target these push messages to users in [!DNL Analytics] segments or custom segments. You can use push messages to re-engage passive users or to convey time-specific and location-specific information because the messages appear outside your app.

Before you can configure Push Messaging, see [Prerequisites to Enable Push Messaging](../c-manage-app-settings/c-mob-confg-app/configure-push-messaging/prerequisites-push-messaging.md#concept_28A61FEE3C7F48F1866BD1995EC43ACE). After you perform these tasks, you must configure push messaging in your app's settings. For more information, see [Configure Push Messaging](../c-manage-app-settings/c-mob-confg-app/configure-push-messaging/configure-push-messaging.md#concept_37A4002F4EA549C99FFD9EBC95554D9C).

## SDK Documentation {#section_49ACA880BA3D44B7B3AAF95571F2DA96}

* For more information about the iOS SDK, see [iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/). 
* For more information about the Android SDK, see [Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/).

## Additional Information

For additional information about messaging, see the following links:

+ [Manage Messages](messages-manage.md)
+ [View Message Reports](view-message-reports.md)
+ [Create a push message](t-create-push-message.md)
+ [Audience: Define and Configure Audience Segments for Push Messages](c-audience-push-message.md)
+ [Experience: Push Message](c-experience--push-message.md)
+ [Schedule: Push Message](c-schedule-push-message.md)
+ [Troubleshooting Push Messaging](c-troubleshooting-push-messaging.md)
+ [Create an in-app message](t-in-app-message.md)
+ [Audience: In-App Message](c-audience-in-app-message.md)
+ [Experience: In-App Message](c-experience-in-app-message.md)
+ [Schedule: In-App Message](c-schedule-in-app-message.md)
+ [Troubleshooting In-App Messaging](in-apps-ts.md)
+ [Trigger an In-App Message when the App is Opened from a Push Message](t-mob-trig-in-app-open-app-from-push.md)