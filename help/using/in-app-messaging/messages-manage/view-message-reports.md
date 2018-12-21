---
description: You can view message reports for in-app and push messages.
keywords: mobile
seo-description: You can view message reports for in-app and push messages.
seo-title: View message reports
solution: Marketing Cloud,Analytics
title: View message reports
topic: Metrics
uuid: 0ac73a81-388f-4dfd-84d5-21b8db4b8c83
---

# View message reports{#view-message-reports}

You can view message reports for in-app and push messages.

1. Click  ![](assets/icon_report.png) in the **[!UICONTROL Report]** column for a message. 
1. (Optional) Create a [Sticky Filter](../../usage/reports-customize/t-sticky-filter.md#task_75B0AD4D58014BB0A5A09FE1B074ECE1) for the report or change the time period by clicking the **[!UICONTROL Calendar]** icon.

>[!TIP]
>
>Depending on the type of message you are viewing, the report might vary

## In-App Messages {#section_90B79BA58E8141F78538C187EB1BF8C7}

If you are viewing reports for an in-app message, the report looks similar to the following illustration:

![](assets/report_message.png)

**Available Metrics** 

<table id="table_01D894234B4F41788D521B3FF0C8E929"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Impression</span> </p> </td> 
   <td colname="col2"> <p>When a message is triggered. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Click through</span> </p> </td> 
   <td colname="col2"> <p>When a user presses the <span class="uicontrol"> Click Through</span> button on an alert or full-screen message, and when a user opens the app from a local notification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Cancel</span> </p> </td> 
   <td colname="col2"> <p>When a user presses the <span class="uicontrol"> Cancel</span> button on an alert or a full-screen message. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Engagement Rate </span> </p> </td> 
   <td colname="col2"> <p>This is a calculated metric from Adobe Analytics and is the result of the number of click throughs divided by the number of impressions. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Push Messages {#section_BEAFD858CA194185B6F88903446058E9}

If you are viewing reports for a push message, the report looks similar to the following illustration:

![](assets/report_message_push.png)

The chart at the top displays the number of users who opened the message.

**Available Metrics** 

<table id="table_08DBD63F0F2249DBA45F9B765AF724A0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Column </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Time </span> </p> </td> 
   <td colname="col2"> <p>The time the message was pushed to devices from Mobile Services. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Status </span> </p> </td> 
   <td colname="col2"> <p>The status of the message. </p> <p>The available statuses are 
     <msgph>
       Cancelled
     </msgph>, 
     <msgph>
       Scheduled
     </msgph>, 
     <msgph>
       Executing
     </msgph>, 
     <msgph>
       Executed
     </msgph>, or 
     <msgph>
       Failed
     </msgph>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Published </span> </p> </td> 
   <td colname="col2"> <p>The number of device tokens that are successfully sent to Apple Push Notification Service/Google Cloud Messaging (APNS/GCM) to send the message to the users devices. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Failed </span> </p> </td> 
   <td colname="col2"> <p>Here are some of the reasons that the number of device tokens that were not successfully sent to APNS/GCM: </p> <p> 
     <ul id="ul_ECE56DBC3A0D45AFB10F114A864889CB"> 
      <li id="li_4497620E65334915A58F56D18B7204BD">An invalid pushID </li> 
      <li id="li_B490028C1BDA4C8DAC7D2CA6876D3CB8">The push platform (APNS, GCM, and so on) that was given to push to does not exist for the job's application. <p>For example, the platform might collect iOS push tokens but does not have APNS service configured. </p> </li> 
     </ul> </p> <p> The message might have failed because the push service was not configured correctly or the Mobile Services system is down. </p> <p> <p>Important:  If you have an unusually large number of failures, check your push services configuration. If push services appears to be configured correctly, contact Adobe Customer Care. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Blacklisted </span> </p> </td> 
   <td colname="col2"> <p>The number of device tokens that are no longer valid to be sent to APNS or GCM. This usually means the app has been uninstalled from the device or the user changed his or her opt-in settings to receive messages. </p> <p> Android and iOS differ about when tokens are counted as blacklisted. Android tokens are immediately shown in the blacklisted count. iOS tokens are initially displayed as published, but based on feedback from APNS, are shown as blacklisted on subsequent messages. </p> </td> 
  </tr> 
 </tbody> 
</table>

