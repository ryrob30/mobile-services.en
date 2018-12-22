---
description: This information can help you troubleshoot your in-app messaging issues.
keywords: mobile
seo-description: This information can help you troubleshoot your in-app messaging issues.
seo-title: Troubleshooting In-App Messaging
solution: Marketing Cloud,Analytics
title: Troubleshooting In-App Messaging
topic: Metrics
uuid: 8813e8d8-bb1e-46ad-83cd-98ae68f73ce6
---

# Troubleshooting In-App Messaging{#troubleshooting-in-app-messaging}

This information can help you troubleshoot your in-app messaging issues.

 If you completed all the requirements for In-App Messaging, but messages do not show up, verify the following items: 

<table id="table_DED57BD89C714BAB8C169B3C96D8D169"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Situation or Issue </th> 
   <th colname="col2" class="entry"> Suggestion </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Are you putting the new configuration and new SDK in the app? </p> </td> 
   <td colname="col2"> <p>Verify that the SDK is version 4.2 or higher and is correctly configured. For a screen shot showing the SDK version, see <a href="https://marketing.adobe.com/resources/help/en_US/mobile/bloodhound/view_hits.html" format="https" scope="external"> View Hits</a> in the Bloodhound documentation. </p> <p> <p>Important:  As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided. </p> </p> <p>Ensure that you have a <a href="/help/ios/messaging-main/messaging/messaging.md" format="https" scope="external"> Messages</a> section in your configuration (the downloaded JSON file) or have a Messages remote endpoint, so that it can be retrieved from dynamic tag management. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> My full screen message in Android is not showing up. I am using the correct SDK, configuration, and my triggers are being met. </p> </td> 
   <td colname="col2"> <p> Did you update your manifest file to define the full screen activity? </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> My local notification message in Android isn't working. </p> </td> 
   <td colname="col2"> <p>Verify that the local notification broadcast receiver is declared in your manifest. </p> <p>For more information, see step #1 in <!--REKHA: <a href="https://docs.adobe.com/content/help/en/mobile-services/android/messaging-android/inapp-messaging/messaging.html#section_380DF56C4EE4432A823940E4AE4C9E91" format="dita" scope="local">Enabling In-App Messaging</a>. --> </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Is the message live? </p> </td> 
   <td colname="col2"> <p>Check the list view in the <span class="uicontrol"> Status</span> column on the <span class="wintitle"> Manage In-App Message</span> page and verify whether the message is live. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Double check the traits/trigger sections. </p> </td> 
   <td colname="col2"> <p> Verify assumptions in data for traits/trigger in bloodhound. </p> <p>Validate the hits in bloodhound. For a screen shot showing the SDK version, see <a href="https://marketing.adobe.com/resources/help/en_US/mobile/bloodhound/view_hits.html" format="https" scope="external"> View Hits</a> in the Bloodhound documentation. </p> <p> <p>Important:  As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Look at <span class="term"> show once</span>, <span class="term"> show always</span>, <span class="term"> show offline</span> settings on the <span class="wintitle"> Audience</span> page. </p> </td> 
   <td colname="col2"> <p> Verify that these settings are correct. On the <span class="wintitle"> Audience</span> page, review the options on the <span class="uicontrol"> Trigger</span> tab, where you can specify how often the message is displayed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> If using launch event as trigger... </p> </td> 
   <td colname="col2"> <p> Launch only fires on a new session. For information on when a session begins, see <span class="term"> lifecycleTimeout</span> in the <a href="/help/ios/configuration/json-config/json-config.md" format="dita" scope="local"> JSON Config</a> file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> I updated my message remotely but my app is still showing the old message. </p> </td> 
   <td colname="col2"> <p> Complete one of the following tasks: 
     <ul id="ul_F9F1B9500C8E45D2A7A37905F149B820"> 
      <li id="li_6A6CB4C5B5354B038EA9A347620FDBA0"> <p>Dynamic tag management might take a few minutes to update its endpoint with your new definition. </p> <p>Give it some time and try again. </p> </li> 
      <li id="li_CF3FBFE18C724BCBA9A0C23F03877575"> <p>The config will only update on a new launch. </p> <p>If the app was restarted in the life cycle session timeout, your new config might not have been downloaded. </p> </li> 
     </ul> </p> 
    <draft-comment> 
     <p>Link to sdk section about lifecycle on how they work and how they are configured. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>My image does not fit exactly into the space provided by the template. </p> </td> 
   <td colname="col2"> <p>The In-App Message full-screen template supports showing an image from a remote server (Image URL) or from the app bundle (Bundled Image). The image should be in a standard image format, for example, JPG, GIF, or PNG. </p> <p>Due to device screens having many different dimensions, the image probably not fit exactly into the space provided by the template. The template always focuses on showing the center of the image and crops (portrait) or fades (landscape) the sides if the image does not fit. </p> <p>Here is the exact placement and sizing rules for each orientation: </p> <p> 
     <ul id="ul_271EE431B7BE4DC7A22D4B6A4B0218D6"> 
      <li id="li_AFCACA75BFA04CBC8D7505D426E24051"> <p><b>Portrait</b>, where the image is scaled to height of 195px for phone, 529px for tablet, centered if image width is smaller than device width, and cropped if image width is greater than device width. </p> </li> 
      <li id="li_DE892D0C39284328A2989ACB0C6E9E64"> <p><b>Landscape</b>, where the image is scaled to 100% of height of device, width is 75% of the device, and with a fade out on the right. </p> </li> 
     </ul> </p> <p>If you have issues with the full-screen template, you can download and use the Custom HTML template. The Custom HTML template provides greater flexibility for images and allows full control of the template. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>My messages are not reflecting changes/updates I have made in the UI. </p> </td> 
   <td colname="col2"> <p> The SDK fetches new/updated messages at the time of a lifecycle launch. This is only when the application is closed/backgrounded for greater than the lifecycle timeout value and then re-opened. </p> <p>Complete the following steps: 
     <ol id="ol_3A4D212EC611448482F18FF39ACE8C3A"> 
      <li id="li_476D7201884F4C539CB471470EBAAE82"> Curl your messages URL in your config file to verify the remote message is updated (for example, <span class="codeph"> curl "https://assets.adobedtm.com/b213090c5204bf94318f4ef0539a38b487d10368/scripts/satellite-542c62859662383b1a0008f4.json"</span>) </li> 
      <li id="li_8C11474CD6B843BA8106BCC4A37810CC"> Close the application. </li> 
      <li id="li_EB5559C9150F4B969936E3BE24942313"> Wait for a time period that is longer than the lifecycleTimeout in the config file. </li> 
      <li id="li_8A513919476A4A32B9C78517D31BC20E"> Open the app, navigate to where the message should be displayed, and verify that it has been updated. </li> 
     </ol> </p> </td> 
  </tr> 
 </tbody> 
</table>

