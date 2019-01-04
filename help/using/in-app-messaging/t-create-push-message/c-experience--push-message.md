---
description: You can configure experience options for push messages and rich push messages, including name, message text, and destination options. You can also configure advanced options, including payload options and custom options for iOS devices.
keywords: mobile
seo-description: You can configure experience options for push messages and rich push messages, including name, message text, and destination options. You can also configure advanced options, including payload options and custom options for iOS devices.
seo-title: Experience  Push Message
solution: Marketing Cloud,Analytics
title: Experience  Push Message
topic: Metrics
uuid: 1a8baf3e-9fea-452c-b0fc-4ba8ac270861
---

# Experience: Push Message{#experience-push-message}

You can configure experience options for push messages and rich push messages, including name, message text, and destination options. You can also configure advanced options, including payload options and custom options for iOS devices.

1. On the [!DNL Audience] page for a new push message, click **[!UICONTROL Experience]**.

   ![](assets/experience-push-message.png)

1. Type a name for this message. 
1. Type information in the following fields in the **[!UICONTROL Message]** section: 

   <table id="table_86AC9803DD0C47168CD179F774B5D573"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Element </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Content </span> </p> </td> 
      <td colname="col2"> <p>Specify the text of your message. You can specify up to a maximum of 140 characters. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Media URL</span> </p> </td> 
      <td colname="col2"> <p>Type the URL of the media file that you plan to use in the push notification message. For requirements to use rich push notifications, see <a href="../../in-app-messaging/t-create-push-message/c-experience--push-message.md#table_C244F841CD724DEDA6EFEADE9F9A7F91" format="dita" scope="local"> Requirements for Rich Push Notifications</a>. </p> <p> <p>Important:  <p>To display an image or a video in a push notification, remember the following: </p> <p> 
         <ul id="ul_228BCE89F55F43DA8B530D064D0DBBAD"> 
         <li id="li_44B8CB9A24F24E8E902BC145D2F34483"> <p>The <span class="codeph"> attachment-url</span> data is handled in the push payload. </p> </li> 
         <li id="li_E5F9447798D24FC0958C15B03047E4EA"> <p>The media URL must be able to handle spikes requests. </p> </li> 
         </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Destination</span> </p> </td> 
      <td colname="col2"> <p>Select a specific destination, such as a web, deep, or hybrid link, to send users when they click-through the message. </p> <p>For more information, see <a href="../../acquisition-main/c-create-destinations.md#concept_73717AC2655E4D1FACFE885FD68D8F17" format="dita" scope="local"> Destinations</a>. </p> <p> <p>Tip: When you use the <span class="uicontrol"> Web Link</span> or <span class="uicontrol"> Custom Link</span> destination types, the destination type is not tracked. Only <span class="uicontrol"> Deep Links</span> are tracked. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   **Requirements for Rich Push Notifications**

   <table id="table_C244F841CD724DEDA6EFEADE9F9A7F91">  
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Requirement </th> 
      <th colname="col2" class="entry"> Details </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p><b>Supported Versions</b> </p> </td> 
      <td colname="col2"> <p> 
      <ul id="ul_1763E91A093B43A7B76FD1D392F2CE4B"> 
         <li id="li_7F35E5E6975F40A1AF167F113D19283B">Android 4.1.0 or later </li> 
         <li id="li_134F2EBB53AF40C8B5D035356A046E08">iOS 10 or later </li> 
      </ul> </p> <p> <p>Important: Remember the following information: 
         <ul id="ul_A890BB2DE9964CE19153177455DC013F"> 
         <li id="li_05E188E6A4A54A26A11172F6CFDF7E2E"> <p>Rich push messages sent to earlier versions will still be sent but only text will be displayed. </p> </li> 
         <li id="li_342F608924AD4319A341D7F1AC76FC77"> <p>There is no watch support at this time. </p> </li> 
         </ul> </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><b>File Formats</b> </p> </td> 
      <td colname="col2"> <p>Here are the supported file formats: </p> <p> 
      <ul id="ul_AC39ABF5B2554DCB8BF8561064BB5A40"> 
         <li id="li_531C9EBC44B14211B17733242DA725AB">Images: JPG and PNG </li> 
         <li id="li_673538A5B65143EC899BC1747F7B27C1">Animations (iOS only): GIF </li> 
         <li id="li_C9057A18A243407FB0BE24A9FA24B781">Videos (iOS only): MP4 </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><b>URL Format</b> </p> </td> 
      <td colname="col2"> <p>HTTPS only </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><b>Sizing</b> </p> </td> 
      <td colname="col2"> <p>Images must be in a 2:1 format or they will be cropped. </p> </td> 
   </tr> 
   </tbody> 
   </table>

   For more information about configuring rich push notifications, see the following content:

      * <a href="/help/android/messaging-main/push-messaging/c-set-up-rich-push-notif-android.md" format="dita" scope="local">Receive Push Notifications in Android</a> 
      * <a href="/help/ios/messaging-main/push-messaging/c-set-up-rich-push-notif-ios.md">Receive Rich Push Notifications in iOS</a>

1. (Optional) Click the **[!UICONTROL Show Advanced Options]** link to configure additional options: 

   <table id="table_8634A4D115D446D9BC738DA525740952"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Element </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Payload: Data</span> </p> </td> 
      <td colname="col2"> <p>Provide a custom push payload in JSON that will be sent to the app through a push or a local notification. </p> <p>The limit for Android and iOS is 4KB. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Apple Options: Category </span> </p> </td> 
      <td colname="col2"> <p>Provide a category for push and local notifications. </p> <p>For more information, see <a href="https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html#//apple_ref/doc/uid/TP40008194-CH4-SW9" format="https" scope="external"> Managing Your App’s Notification Support</a> in the <i>iOS Developer Library</i>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Apple Options: Sound</span> </p> </td> 
      <td colname="col2"> <p>Provide the name of the sound file in your app bundle to play. A default alert sound plays if not set. </p> <p>For more information, see <a href="https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html#//apple_ref/doc/uid/TP40008194-CH4-SW10" format="https" scope="external"> Managing Your App's Notificaton Support</a> in the <i>iOS Developer Library</i>. </p> <p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><span class="uicontrol"> Apple Options: Content Available </span> </p> </td> 
      <td colname="col2"> <p>Select this option so that when the message arrives, iOS wakes up your app in the background and allows your app to execute code based on the message payload. </p> <p>For more information, see <a href="https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html#//apple_ref/doc/uid/TP40008194-CH8-SW1" format="https" scope="external"> Apple Push Notification Service</a> in the <i>iOS Developer Library</i> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. (Optional) Preview the layout of your message by clicking following icons:

   <table id="table_1F3A432BA41C4648818387A6A42A270C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Icon </th> 
      <th colname="col2" class="entry"> Description </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>x Summary </p> </td> 
      <td colname="col2"> <p>Hide the preview pane. Click <img src="assets/icon_preview.png" id="image_B1F0C3DAA1174AEF9E02D5F9C2821E2C" /> to redisplay the preview pane. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><img src="assets/icon_orientation.png" id="image_BB8B902423FD4D4D98FCF20B703766D8" /> </p> </td> 
      <td colname="col2"> <p>Click to change the orientation of the preview from portrait to landscape mode. For watches, the orientation changes from a round watch face to a square watch face. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><img src="assets/icon_watch.png" id="image_232BFE8DC97A4FE4ADF9E8C5D52618FF" /> </p> </td> 
      <td colname="col2"> <p>Click to preview your message as it will appear on users's watches. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><img src="assets/icon_phone.png" id="image_FA00AC03DDC14C9FB615EC48CF4AE13B" /> </p> </td> 
      <td colname="col2"> <p>Click to preview your message as it will appear on users's mobile phones. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p><img src="assets/icon_tablet.png" id="image_9894F392F00649A889D445C52DE3E384" /> </p> </td> 
      <td colname="col2"> <p>Click to preview your message as it will appear on users's tablets. </p> </td> 
   </tr> 
   </tbody> 
   </table>

   At the bottom of the preview pane, you can view a description of the audience that you selected in the previous step. 

1. (Optional) Click **[!UICONTROL Test]** to push your message to specified devices for testing purposes. 
1. Select the service and type the push tokens for at least one device to which you want to push the message.

   Specify the tokens in a comma-separated list to push the message to more than one device. 
1. Configure [Schedule options](../../in-app-messaging/t-create-push-message/c-schedule-push-message.md#concept_F7B31A14470E4EF69ECAC264F52084A3).

