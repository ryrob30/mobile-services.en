---
description: You must complete these tasks before configuring Push Messaging in applications.
keywords: mobile
seo-description: You must complete these tasks before configuring Push Messaging in applications.
seo-title: Prerequisites to Enable Push Messaging
solution: Marketing Cloud,Analytics
title: Prerequisites to Enable Push Messaging
topic: Metrics
uuid: 194e6e07-b794-4152-a838-a4125c3292d4
---

# Prerequisites to Enable Push Messaging{#prerequisites-to-enable-push-messaging}

You must complete these tasks before configuring Push Messaging in applications.

<table id="table_38C718AFE2384FCB89EA70AD7B45226F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Task </th> 
   <th colname="col2" class="entry"> Instructions </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Enable the Experience Cloud for Your Company. </p> </td> 
   <td colname="col2"> <p>Your <span class="keyword"> Adobe Analytics</span> Company must be <span class="keyword"> Experience Cloud</span> enabled. You can verify this with your Adobe account executive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Install and Configure the Mobile SDK. </p> </td> 
   <td colname="col2"> <p> 
     <ol id="ol_A41CC8336C1343B5A2C51DBE9E500086"> 
      <li id="li_2723BBC83BB34365B56BB8443A9AFA3D"><b>Install the Mobile SDK</b> <p>The Push Messaging feature requires that you download and install the appropriate 4.6 (or later) Mobile SDK. </p> <p>For more information, see the following content: </p> <p> 
        <ul id="ul_DB6A44A2FF724B5BB36973FDFB8353A5"> 
         <li id="li_6323CE2240FD490292B39884BB00559C"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/" format="http" scope="external"> Android SDK 4.x for Experience Cloud Solutions</a> </li> 
         <li id="li_2B97BA81591747638D620A23881411F6"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/" format="http" scope="external"> iOS SDK 4.x for Experience Cloud Solutions</a> </li> 
        </ul> </p> </li> 
      <li id="li_D5272F153A144E4F8D518582019F06F5"><b>Configure Push Services</b> <p>You must configure push services in the Mobile SDK. </p> <p>For more information, see the following content: </p> <p> 
        <ul id="ul_9D19940E312448529CC554019A980DAD"> 
         <li id="li_B6B6E064BBDC451590D7F615EBE30742"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/push_messaging.html" format="https" scope="external"> Android: Push Messaging</a> </li> 
         <li id="li_1F84BB2FF4D741A8B37F5F5850635AE1"><a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/push_messaging.html" format="https" scope="external"> iOS: Push Messaging</a> </li> 
        </ul> </p> </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Log in to the <span class="keyword"> Mobile</span> Core Service using your Adobe ID. </p> </td> 
   <td colname="col2"> <p> <p>Important:  To use the Push Services functionality users must log in to the Mobile Core Service by using their Adobe ID and their Analytics account must be linked to their Adobe IDs. Push Services functionality is not available if users log in using their existing Adobe Analytics accounts. </p> </p> <p>If users do not have Adobe IDs, complete the following steps: </p> <p> 
     <ol id="ol_CAADA58D85D94151B4EC3B1B67807644"> 
      <li id="li_BE503F97BB4A46E9925EB80AACE2E089"> <p><b>Experience Cloud Administrator</b> invites users to the Experience Cloud. </p> </li> 
      <li id="li_08858B4EBF334AF9AB83BAD70F9B9A69"> <p><b>Users</b> create a personal Adobe ID using the instructions received from the <span class="keyword"> Experience Cloud</span> administrator. </p> <p>An email message is automatically sent to each user after the administrator completes the previous step. </p> </li> 
      <li id="li_207BD71DF1E7484D9141D93BC5715CED"> <p><b>Users</b> log in to <span class="keyword"> Mobile</span> using their Adobe ID. </p> </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Link Users' Accounts in the <span class="keyword"> Experience Cloud.</span> </p> </td> 
   <td colname="col2"> <p>Each user must link the <span class="keyword"> Analytics</span> solution account from the <span class="keyword"> Experience Cloud</span> organization. </p> <p> 
     <ol id="ol_C6AF47D454584812AC33020B3E4CFE7E"> 
      <li id="li_D432FAD47BB340429542ECAEA7968FAB"> <p>To sign in to the <span class="keyword"> Experience Cloud</span> with an Adobe ID, type <a href="https://marketing.adobe.com" format="https" scope="external"> https://marketing.adobe.com</a> in a browser. </p> </li> 
      <li id="li_1C67A1C3186B4AB2B38032B71C780DA4"> <p>In the upper right corner, select the <span class="keyword"> Analytics</span> company name. </p> </li> 
      <li id="li_99FEAF181EEC4E5FA757661E724903C6"> <p>Click <span class="uicontrol"> Add Organization</span> and select <span class="uicontrol"> Adobe SiteCatalyst/Adobe Social</span> from the drop-down list. </p> </li> 
      <li id="li_7122CC3B32F64C5D986F0C687DC7F869"> <p>Type the company name, your legacy credentials for the specified company, and click <span class="uicontrol"> Link Account</span>. </p> <p>The Adobe ID is now linked to your <span class="keyword"> Analytics</span> account, company, and log-in credentials. </p> </li> 
     </ol> </p> <p>For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html" format="html" scope="external"> Troubleshooting Account Linking</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configure Push Services and the SDK ID service in the Mobile User Interface </p> </td> 
   <td colname="col2"> <p>Before you enable the ID service for your app, the <span class="uicontrol"> Push Services</span> section is disabled. But, after you <a href="../../../c-manage-app-settings/c-mob-confg-app/t-config-visitor.md#task_568C5F05E4E044E9BCCCF91ABBA736F7" format="dita" scope="local"> enable the ID service</a>, the <span class="uicontrol"> Push Services</span> section is enabled. </p> <p> </p> <p> <p>Remember: You must click <span class="uicontrol"> Save</span> to save your changes and refresh the <span class="uicontrol"> Push Services</span>. </p> </p> <p> <p>Important:  You can configure one app store app for Apple and one for Google in each report suite. If you need additional apps, for example, one for a production environment and one for a dev environment, set up a new app store app and a new report suite for each environment. </p> </p> 
    <ul id="ul_F07CD0AD2A854C4CAB366CDF01982C8C"> 
     <li id="li_B05B03A136C34334A82C8A1BE7DA2DBF"> <p>For <b>Apple</b>, drag and drop your private key and/or certificate. If your private key is password-encrypted, type its password. </p> <p> 
       <ul id="ul_1A7EBD6CB21341B4A9A6123BDAD33E2B"> 
        <li id="li_B588CD717FA54A16BB5A4DDB22CF358A">For the <b>Private Key</b>, drag and drop your private-key file into the box. You can also click <span class="uicontrol"> Browse</span> to select the file. <p>This file contains the private key. The certificate might also be included in this file (<span class="filepath"> .p12</span>, <span class="filepath"> pkcs12</span>, <span class="filepath"> .pfx</span>, <span class="filepath"> .key</span>,<span class="filepath"> .pem</span>). </p> </li> 
        <li id="li_3677E3AE8BCB4EB0B56C621D5816D7A9">For the <b>Private Key Password</b>, if your private-key file is encrypted, type the password. <p>(Conditional) For the <b>Certificate</b>, drag and drop your certificate file into the box. You can also click <span class="uicontrol"> Browse</span> to select the file. </p> <p>This field is not required if the private-key file also contains the certificate (<span class="filepath"> .cert</span>, <span class="filepath"> .cer</span>, <span class="filepath"> .crt</span>, <span class="filepath"> .pem</span>). </p> </li> 
       </ul> </p> </li> 
     <li id="li_C5245B6DA72747BB800E575527749B65"> <p>For <b>Google</b>, specify the API key for the app. </p> </li> 
    </ul> <p>Click <span class="uicontrol"> Test</span> to validate that the app and Mobile Services are configured correctly. This option is useful for debugging and troubleshooting. </p> <p> Type the device's push tokens that you want to send the message. You can send the message to multiple devices by specifying tokens in a comma-separated list. </p> <p><img href="assets/push_test_list.png" id="image_8C4DC06DAF444BF298F380CF24F41A6D" /> </p> </td> 
  </tr> 
 </tbody> 
</table>
