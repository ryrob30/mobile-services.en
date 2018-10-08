---
description: This information helps you troubleshoot push messaging.
keywords: mobile
seo-description: This information helps you troubleshoot push messaging.
seo-title: Troubleshooting Push Messaging
solution: Marketing Cloud,Analytics
title: Troubleshooting Push Messaging
topic: Metrics
uuid: 38fe3dc6-a13c-4ee0-b4e2-368a82830966
index: y
internal: n
snippet: y
translate: y
---

# Troubleshooting Push Messaging

This information helps you troubleshoot push messaging.

<table id="table_AFEA60DA4FDE49A9825D1763CA2B284C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Situation or issue </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Why are there sometimes delays sending push messages? </p> </td> 
   <td colname="col2"> <p>The following types of delays might be associated with push messages for <span class="keyword"> Mobile Services</span>: </p> 
    <ul id="ul_2D640D3BD7DE4DA1914946F2206154A8"> 
     <li id="li_46B67732DA274D6CABA6DCD63A444128"> <p><b>Waiting for Analytics Hits</b> </p> <p>Every report suite has a setting to determine when to process incoming <span class="keyword"> Analytics</span> hits. The default is 1 hour on the hour. The actual processing of <span class="keyword"> Analytics</span> hits might take up to 30 minutes but is typically 15-20 minutes. </p> <p>For example, a report suite processes hits every hour. If you factor in the processing time of a maximum of 30 minutes, it could take up to 90 minutes for an incoming hit to be available for a push message. If a user launched the app at 9:01 AM, the hit would show up in the <span class="keyword"> Mobile Services</span> UI as a new unique user between 10:15 to 10:30 AM. </p> </li> 
     <li id="li_DADD236C565A45B5988AC33A96EEE822"> <p><b>Waiting for Push Service</b> </p> <p>The push service (APNS or GCM) might not immediately send out the message. Although uncommon, we have seen a delay of 5-10 minutes. On the <span class="wintitle"> Messages</span> page, you can verify that the push message has been sent to the push service by clicking the <span class="uicontrol"> View</span> link for the message. In the report, the number of successful sends to the push service is listed in the <span class="uicontrol"> Published</span> column. </p> <p>Tip: The push services do not guarantee a message will be sent. For more information about the reliability of services, see the appropriate documentation: <p> 
        <ul id="ul_C9EF9BD024854EB6A48DF670244A0195"> 
         <li id="li_FA3EC8AE3F764B708C690E2CC7E7224C"> <p><b>APNS</b>: <a href="https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html#//apple_ref/doc/uid/TP40008194-CH8-SW5" format="html" scope="external"> Quality of Service</a> </p> </li> 
         <li id="li_37425C4D61AF45BF8CA66F10EC63000D"> <p><b>GCM</b>: <a href="https://developers.google.com/cloud-messaging/concept-options#lifetime" format="https" scope="external"> Lifetime of a Message</a> </p> </li> 
        </ul> </p> </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Why are my push messages being cut off or are not expanding? </p> </td> 
   <td colname="col2"> <p>For some Android devices, you might need to use <span class="codeph"> NotificationCompat.BigTextStyle</span> when displaying messages. </p> </td> 
  </tr> 
 </tbody> 
</table>

