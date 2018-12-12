---
description: Adobe Mobile and the Adobe Mobile SDK allow you to send push messages to your users. The SDK also allows you to easily report users who have opened your app after clicking through a push message.
seo-description: Adobe Mobile and the Adobe Mobile SDK allow you to send push messages to your users. The SDK also allows you to easily report users who have opened your app after clicking through a push message.
seo-title: Push Messaging
solution: Marketing Cloud,Analytics
title: Push Messaging
topic: Developer and implementation
uuid: 729d4010-3733-4dff-b188-ad45bd3e7cc4
index: y
internal: n
snippet: y
---

# Push Messaging{#push-messaging}

Adobe Mobile and the Adobe Mobile SDK allow you to send push messages to your users. The SDK also allows you to easily report users who have opened your app after clicking through a push message.

>[!IMPORTANT]
>
>To use push messaging, you **must** have SDK version 4.6 or later.

>[!IMPORTANT]
>
>Do not manually set the Experience Cloud ID inside your app. This causes the creation of a new unique user that will not receive push messages because of its opt-in status. For example, a user has opted-in to receive push messages logs in to your app. After logging in, if you manually set the ID inside your app, a new unique user is created who has not opted to receive push messages. This new user will not receive your push messages.

This section contains the following information:

* [Prerequisites](../../messaging-main/push-messaging/push-messaging.md#section_06655ABE973743DC965897B229A2118D) 
* [Enable Push Messaging](../../messaging-main/push-messaging/push-messaging.md#section_CBD63C5B11FE4424BC2BF552C23F2BD9)

## Prerequisites {#section_06655ABE973743DC965897B229A2118D}

* Add the library to your project and implement [lifecycle metrics](../../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05). 
* SDK must be [enabled for the ID Service](https://marketing.adobe.com/resources/help/en_US/mobile/t_config_visitor.html).

<a id="section_FF244934885C462E86F1F0F17C20D27E"></a>

>[!IMPORTANT]
>
>Moving your app to a new report suite is not supported. If you migrate to a new report suite, your push configuration can break, and messages might not be sent.

## Enable Push Messaging {#section_CBD63C5B11FE4424BC2BF552C23F2BD9}

>[!TIP]
>
>If your app is already set up to use messaging by using Google Cloud Messaging (GCM), some of the following steps might already be completed.

1. Verify that `ADBMobileConfig.json` contains the required settings for push messaging.

   The `"marketingCloud"` object must have its `"org"` property configured for push messaging. 

   ```js
   "marketingCloud": { 
     "org": <org-id-string> 
    }
   ```

1. Obtain the registration ID/token by using the GCM or Firebase Cloud Messaging (FCM) APIs.

    * **GCM**

        * For more information about setting up GCM, see [Set up a GCM Client App on Android](https://developers.google.com/cloud-messaging/android/client). 
        * To implement a sample app, see [Google Samples](https://github.com/googlesamples/google-services/tree/master/android/gcm).

          ```js        
          InstanceID instanceID = InstanceID.getInstance(this); 
          String token = instanceID.getToken(getString(R.string.gcm_defaultSenderId), GoogleCloudMessaging.INSTANCE_ID_SCOPE, null);
          ```

    * **FCM **

        * For more information about setting up FCM, see [Set Up a Firebase Cloud Messaging Client App on Android](https://firebase.google.com/docs/cloud-messaging/android/client).

          ```js        
          String token = FirebaseInstanceId.getInstance().getToken();
          ```

1. The registration ID/token must be passed to the SDK by using the `Config.setPushIdentifier(final String registrationId)` method.

   ```js
   Config.setPushIdentifier(token); // token was obtained in step 2
   ```

1. Enable reporting by passing your activity in the `collectLifecycleData` method.

   Here are the requirements to enable push click-through reporting:

    * In your implementation of `GCMListenerService`, the Bundle object that contains the message data, which is passed into the `onMessageReceived` method, must be added to the Intent that is used to open the target activity on a click-through.

      This can be done using the method `putExtras` ( [Click here for more info](https://developer.android.com/reference/android/content/Intent.html#putExtras(android.os.Bundle))). 
    
    * In the target activity of the clickthrough, the activity must be passed into the SDK with the `collectLifecycleData` call.

      Remember the following information:

        * Use `Config.collectLifecycleData(this)` or `Config.collectLifecycleData(this, contextData)`. 
        
        * Do **not** use `Config.collectLifecycleData()`.

