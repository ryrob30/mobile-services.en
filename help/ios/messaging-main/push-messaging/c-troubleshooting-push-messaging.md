---
description: This information helps you troubleshoot push messaging.
keywords: mobile
seo-description: This information helps you troubleshoot push messaging.
seo-title: Troubleshooting Push Messaging
solution: Marketing Cloud,Analytics
title: Troubleshooting Push Messaging
topic: Metrics
uuid: 87d7dcb6-82a8-46e3-a6ed-7f895a22f2af
index: y
internal: n
snippet: y
---

# Troubleshooting Push Messaging{#troubleshooting-push-messaging}

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
    <ul id="ul_730B9B49AFF9499B9063C235E98EB129"> 
     <li id="li_0CF7BF0813694A58B445B2BA07D31B35"> <p><b>Waiting for Analytics Hits</b> </p> <p>Every report suite has a setting to determine when to process incoming <span class="keyword"> Analytics</span> hits. The default is 1 hour on the hour. The actual processing of <span class="keyword"> Analytics</span> hits might take up to 30 minutes but is typically 15-20 minutes. </p> <p>For example, a report suite processes hits every hour. If you factor in the processing time of a maximum of 30 minutes, it could take up to 90 minutes for an incoming hit to be available for a push message. If a user launched the app at 9:01 AM, the hit would show up in the <span class="keyword"> Mobile Services</span> UI as a new unique user between 10:15 to 10:30 AM. </p> </li> 
     <li id="li_079F7EEACC474C25B65E3A1E111A5EEB"> <p><b>Waiting for Push Service</b> </p> <p>The push service (APNS or GCM) might not immediately send out the message. Although uncommon, we have seen a delay of 5-10 minutes. On the <span class="wintitle"> Messages</span> page, you can verify that the push message has been sent to the push service by clicking the <span class="uicontrol"> View</span> link for the message. In the report, the number of successful sends to the push service is listed in the <span class="uicontrol"> Published</span> column. </p> <p>Tip: The push services do not guarantee a message will be sent. For more information about the reliability of services, see the appropriate documentation: <p> 
        <ul id="ul_C9EF9BD024854EB6A48DF670244A0195"> 
         <li id="li_FA3EC8AE3F764B708C690E2CC7E7224C"> <p><b>APNS: </b><a href="https://developer.apple.com/documentation/usernotifications" format="https" scope="external"> Quality of Service</a> </p> </li> 
         <li id="li_37425C4D61AF45BF8CA66F10EC63000D"> <p><b>GCM: </b><a href="https://developers.google.com/cloud-messaging/concept-options#lifetime" format="https" scope="external"> Lifetime of a Message</a> </p> </li> 
        </ul> </p> </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>How do I renew my Apple Push Service Certificate? </p> </td> 
   <td colname="col2"> <p>Sending push messages requires a valid Push Service Certificate. <span class="keyword"> Mobile Services</span> will notify you when your certificate is close to expiring or has expired. If you receive this notification, complete the following steps to renew your certificate: </p> <p> 
     <ol id="ol_8D9BDB5388F848BC95B71017D3D2F0E8"> 
      <li id="li_744022E8C3674A9AB79A9E06C730F75B">Click <span class="uicontrol"> Manage App Settings.</span> </li> 
      <li id="li_EA80A676E5B0485F8121F7B1B3AEAE98">To delete the current certificate, scroll to <span class="uicontrol"> Push Services</span> and click <span class="uicontrol"> Delete</span>. <p style="text-align: center;"><img href="assets/pushcert.png" id="image_AFA6904CE9024AA7A6426337A9244AB2" /> </p> </li> 
      <li id="li_381FE92087B944419B7E54CF3FB06152">Configure and test a new certificate. <p>For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/mobile/prerequisites_push_messaging.html" format="html" scope="external"> Prerequisites to Enable Push Messaging</a> </p> </li> 
      <li id="li_D0AE7E2DB99F4B12BB886D021D02078C">Click <span class="uicontrol"> Save</span>. </li> 
     </ol> </p> </td> 
  </tr> 
 </tbody> 
</table>

