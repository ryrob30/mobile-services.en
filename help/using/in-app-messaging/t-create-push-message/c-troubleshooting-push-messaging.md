---
description: This information can help you troubleshoot push messaging.
keywords: mobile
seo-description: This information can help you troubleshoot push messaging.
seo-title: Troubleshooting Push Messaging
solution: Marketing Cloud,Analytics
title: Troubleshooting Push Messaging
topic: Metrics
uuid: c7be4ab7-0cfe-4296-84a8-01412f4fd93f
---

# Troubleshooting Push Messaging{#troubleshooting-push-messaging}

This information can help you troubleshoot push messaging.

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
   <td colname="col2"> <p>The following types of delays might be associated with push messages for <span class="keyword"> Mobile Services</span>: </p> <p> 
     <ul id="ul_2D640D3BD7DE4DA1914946F2206154A8"> 
      <li id="li_46B67732DA274D6CABA6DCD63A444128"><b>Waiting for Analytics Hits</b> <p>Every report suite has a setting to determine when to process incoming <span class="keyword"> Analytics</span> hits. The default is every 1 hour. </p> <p> The actual processing of <span class="keyword"> Analytics</span> hits might take up to 30 minutes, but is typically 15-20 minutes. For example, a report suite processes hits every hour. When you factor the required processing time of 30 minutes max, it can take up to 90 minutes for an incoming hit to be available for a push message. If a user launched the app at 9:01 AM, the hit would appear in the <span class="keyword"> Mobile Services</span> UI as a new unique user between 10:15 to 10:30 AM. </p> </li> 
      <li id="li_DADD236C565A45B5988AC33A96EEE822"><b>Waiting for the Push Service</b> <p>The Push Service (APNS or GCM) might not immediately send out the message. Although uncommon, there have been occurrences of wait times up to 5-10 minute. </p> <p>You can verify that the push message has been sent to the Push Service by looking in the <span class="uicontrol"> Report</span> view of the Push Message, finding the message in the <span class="uicontrol"> Message History</span> table, and looking at the <span class="uicontrol"> Published</span> count. <p>Tip:  This count is the number of successful sends to the Push Service(s). </p> </p> <p>The Push Services do not guarantee that a message will be sent. For more information about the reliability of service, see the following content: 
        <ul id="ul_D3CA7889C22D4F218C2369944D265510"> 
         <li id="li_27D06381ED7D462D823050C80445F5E6"><b>APNS: </b><a href="https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/APNSOverview.html#//apple_ref/doc/uid/TP40008194-CH8-SW5l" format="html" scope="external"> Quality of Service</a>. </li> 
         <li id="li_5AEE192DC11B493F803A8110F3AE6EF2"><b>GCM: </b><a href="https://developers.google.com/cloud-messaging/concept-options#lifetime" format="html" scope="external"> Lifetime of a Message</a>. </li> 
        </ul> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Why is my Android GCM API key invalid? </p> </td> 
   <td colname="col2"> <p><b>Invalid API key</b> </p> <p>Your API key might be invalid for the following reasons: </p> <p> 
     <ul id="ul_2259DA116928464987B8913D01794430"> 
      <li id="li_7EDBEFE26D5F4C8FBEC9C2224828D390">The API key that you provided is not a server key with the correct GCM API key value. </li> 
      <li id="li_E505A406614E4FAC91B77177A2CB9652">The server key has whitelisted the IPs and is blocking Adobe's servers from sending a push message. </li> 
     </ul> </p> <p><b>Determine the validity of the API key</b> </p> <p>To determine the validity of your API key, run the following command: </p> <p><b>Android</b> </p> 
    <code class="syntax java">
     #&nbsp;api_key=YOUR_API_KEY#&nbsp;curl&nbsp;--header&nbsp;"Authorization:&nbsp;key=$api_key"&nbsp;\&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;--header&nbsp;Content-Type:"application/json"&nbsp;\&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://gcm-http.googleapis.com/gcm/send&nbsp;\&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-d&nbsp;"{\"registration_ids\":[\"ABC\"]}"
    </code> <p>A returned 401 HTTP status code means that your API key is invalid. Otherwise, you will see something similar to this: </p> 
    <code class="syntax java">
     {"multicast_id":6782339717028231855,"success":0,"failure":1,"canonical_ids":0,"results":[{"error":"InvalidRegistration"}]}
    </code> <p>You can also check the validity of a registration token by replacing <span class="codeph"> "ABC"</span> with the token. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Why is my APNS cert not working? </p> </td> 
   <td colname="col2"> <p><b>Invalid Certificate</b> </p> <p>Your APNS certificate might be invalid for the following reasons: </p> <p> 
     <ul id="ul_58F45F7223CF4DC0A6EFD69807B6ABB8"> 
      <li id="li_CFB6258079E54945A68E4372BB2192E2">You might be using a sandbox certificate instead of the production certificate. </li> 
      <li id="li_519ED2AFA6014F7486B0230B862F0626">You are using a new production/sandbox certificate that is not supported. </li> 
      <li id="li_2D727A1CEB1E4A3A9098F55BF9DA05E0">You are using .p8 file instead of a .p12 file. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Resolving push message failures </td> 
   <td colname="col2"> <p><b>An Example</b> </p> <p>The following example illustrates how you can resolve a push failure when using a VRS. </p> <p>The following customer has two iOS apps: </p> <p> 
     <ul id="ul_FB9CC3EE1C94405383FB0832E3CF8EAF"> 
      <li id="li_BA9F519BB05D43B6A34B3D202D7D240D">App Name: PhotoShop_app_iOS 
       <ul id="ul_6D14264A6BC14931B6A426C145AAB907"> 
        <li id="li_F606AE05DD6F4E399004C0D5E1903912">Parent RSID: AllAdobe PhotoShop_apps </li> 
        <li id="li_D545414062874B65917439EA9E082315">VRSID: PhotoShop_iOS_app_SF </li> 
        <li id="li_278B3961637440B88EB892071768D4A9">VRSID Definition Segment: <span class="codeph"> a.appid contains “PhotoShop_iOS_app_SF”</span> </li> 
       </ul> </li> 
      <li id="li_B044F54889674162977B4A0138C32941">App Name: PhotoShop_app_iOS 
       <ul id="ul_EBC641A23E4E476BB26D913E57288AB6"> 
        <li id="li_F78D5AC0D58D4BFCBFC9C141E2163BFC">Parent RSID: AllAdobe PhotoShop_apps </li> 
        <li id="li_DBAC785F7890428CA786F5E94FDD5995">VRSID: PhotoShop_iOS_app_LA </li> 
        <li id="li_1F1AB96B357F4B01B4BDF34AE71C8E80">VRSID Definition Segment: <span class="codeph"> a.os contains “iOS”</span> </li> 
       </ul> </li> 
     </ul> </p> <p>In this example, if a Photoshop employee sends a push to the PhotoShop_iOS_app_SF app, all PhotoShop_iOS_app_SF app users will receive the push message as expected. But, if the employee sends a message to the PhotoShop_iOS_app_LA app, because its VRSID Definition Segment is incorrect (<span class="codeph"> iOS</span> instead of <span class="codeph"> a.os contains "PhotoShop_iOS_app_LA"</span>), the message is sent to <b>all</b> iOS users in AllAdobe PhotoShop_apps. Although the message will still go to PhotoShop_iOS_app_LA users, the message will also blacklist the push IDs for PhotoShop_iOS_app_SF users because the PhotoShop_iOS_app_SF app has a different certificate. If the segment had been defined as <span class="codeph"> a.os contains “PhotoShop_iOS_app_LA”</span>, the push message would have been sent to only PhotoShop_iOS_app_LA users. </p> <p> If passed with the PhotoShop_IOS_app_LA push certificate, the push identifiers for the PhotoShop_iOS_app_SF will come back as <span class="codeph"> invalid</span>. </p> <p> <p>Warning: After you create a push message for an app that is using a VRS and click <span class="uicontrol"> Save &amp; Send</span>, an alert appears that reminds you ensure that each app that is listed <b>must</b> have a valid certificate. If each app does <b>not</b> have a valid certificate, your audience segments might be indefinitely blacklisted, and you might not be able to send future push messages to the affected users. </p> </p> <p> For more information about audience segments, see <a href="../../in-app-messaging/t-create-push-message/c-audience-push-message.md#concept_2A4EFA42181B41A98477C0E9164E017E" format="dita" scope="local"> Audience: Define and Configure Audience Options for Push Messages</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
