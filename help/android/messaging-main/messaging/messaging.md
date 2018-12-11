---
description: You can deliver in-app messages that are triggered from any analytics data or event. After the implementation, messages are dynamically delivered to the app and do not require a code update.
seo-description: You can deliver in-app messages that are triggered from any analytics data or event. After the implementation, messages are dynamically delivered to the app and do not require a code update.
seo-title: In-App Messaging
solution: Marketing Cloud,Analytics
title: In-App Messaging
topic: Developer and implementation
uuid: 351ee3d2-80b9-4f2d-9696-21f274d89f5a
index: y
internal: n
snippet: y
---

# In-App Messaging{#in-app-messaging}

You can deliver in-app messages that are triggered from any analytics data or event. After the implementation, messages are dynamically delivered to the app and do not require a code update.

>[!IMPORTANT]
>
>To use in-app messaging, you **must** have SDK version 4.2 or later.

You can create messages and the rules in Adobe Mobile services that define when messages are displayed. For more information, see [Create an in-app message](https://marketing.adobe.com/resources/help/en_US/mobile/?f=t_in_app_message). To display in-app messages, updates must be made to the SDK. You can complete these steps even if you have not yet defined any messages. After you define messages, they will be delivered dynamically to your app and displayed without an app store update.

This topic contains the following information:

* [Enabling In-App Messaging](../../messaging-main/messaging/messaging.md#section_380DF56C4EE4432A823940E4AE4C9E91) 
* [Tracking In-App Messages](../../messaging-main/messaging/messaging.md#section_B85CDF6929564AAEA79338B55E5CB1E8) 
* [Local Fallback Image](../../messaging-main/messaging/messaging.md#section_DEACC1CE549B4573B556A44A52409941) 
* [Configuring Notification Icons](../../messaging-main/messaging/messaging.md#section_DDA28BDBCBB748BCBECF3AB50A177D48)

## Enabling In-App Messaging {#section_380DF56C4EE4432A823940E4AE4C9E91}

1. Add the [library to your project and implement lifecycle](../../getting-started/dev-qs.md#concept_13176B6E37F547D6935E37125F457972). 
1. Update [!DNL AndroidManifest.xml] to declare the full screen activity and enable the Message Notification Handler:

   ```java
   <activity  
   android:name="com.adobe.mobile.MessageFullScreenActivity"  
   android:theme="@android:style/Theme.Translucent.NoTitleBar" /> 
   <receiver android:name="com.adobe.mobile.MessageNotificationHandler" />
   ```

   If you selected a modal layout, select one of the following themes for the message:

    * `Theme.Translucent.NoTitleBar.Fullscreen` 
    * `Theme.Translucent.NoTitleBar` 
    * `Theme.Translucent`

   For example: 

   ```java
   <activity 
   android:name="com.adobe.mobile.MessageFullScreenActivity" 
   android:theme="@android:style/Theme.Translucent.NoTitleBar.Fullscreen" 
   android:windowSoftInputMode="adjustUnspecified|stateHidden" /> 
   <receiver android:name="com.adobe.mobile.MessageNotificationHandler" />
   ```

1. Import the library: 

   ```java
   import com.adobe.mobile.*;
   ```

1. In each `collectLifecycleData` call, pass `this` to provide a reference to your current activity: 

   ```java
   @Override 
   public void onResume() { 
       Config.collectLifecycleData(this); 
   }
   ```

1. Verify that `ADBMobileConfig.json` contains the required settings for in-app messaging.

   >[!IMPORTANT]
   >
   >`messages` or `remotes` is required.

   For in-app messages to be dynamically updated on launch, the `remotes` object must be present and properly configured: 

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

   If this object is not configured, download an updated `ADBMobileConfig.json` from Adobe Mobile services. For more information, see [Before You Start](../../getting-started/requirements.md#concept_2FA4E790CA1646FFB44488CF017821DE).

## Tracking In-App Messages {#section_B85CDF6929564AAEA79338B55E5CB1E8}

The Android Mobile SDKs track the following metrics for your in-app messages:

* For full screen and alert style in-app messages:

    * **Impressions**: when user triggers an in-app message. 
    * **Click throughs**: when user presses the **[!UICONTROL Click through]** button. 
    
    * **Cancels**: when user pushes the **[!UICONTROL Cancel]** button.

* For custom, full screen in-app messages, the HTML content in the message needs to include the correct code to notify the SDK tracking about the following buttons:

    * **Click-through** (redirect) example tracking: `adbinapp://confirm/?url=https://www.yoursite.com` 
    
    * **Cancel** (close) example tracking: `adbinapp://cancel`

## Local Fallback Image {#section_DEACC1CE549B4573B556A44A52409941}

When creating a full-screen message, you can optionally specify a fallback image. If your message cannot retrieve its intended image from the web, the SDK attempts to load the image with the same name from your application’s assets folder. This allows you to show your message in its original form, even if the user is offline, or the predetermined image is unreachable.

>[!IMPORTANT]
>
>The fallback image asset name is specified when you configure the message in Adobe Mobile services, and you need to ensure that the specified resource is available.

## Configuring Notification Icons {#section_DDA28BDBCBB748BCBECF3AB50A177D48}

The following methods allow you to configure the small and large icons that appear in the notification area, and the large icon that is displayed when notifications appear in the notification drawer. 

<table id="table_AD6469D4C9024D99A6D7EDD830112285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="codeph"> Config.setSmallIconResourceId(int resourceId) </span> </td> 
   <td colname="col2"> <p>Set the small icon that will be used for notifications that are created by the SDK. This icon appears in the status bar and is the secondary image that is displayed shown when the user sees the complete notification in the notification center. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setSmallIconResourceId(final&amp;nbsp;int&amp;nbsp;resourceId); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Config.setSmallIconResourceId(R.drawable.appIcon); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> Config.setLargeIconResourceId(int resourceId) </span> </td> 
   <td colname="col2"> <p>Set the large icon that will be used for notifications that are created by the SDK. This icon will be the primary image that is displayed when the user sees the complete notification in the notification center. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax java">
      public&amp;nbsp;static&amp;nbsp;void&amp;nbsp;setLargeIconResourceId(final&amp;nbsp;int&amp;nbsp;resourceId); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax java">
      Config.setLargeIconResourceId(R.drawable.appIcon); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

