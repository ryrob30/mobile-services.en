---
description: This information helps you troubleshoot in-app messaging.
keywords: mobile
seo-description: This information helps you troubleshoot in-app messaging.
seo-title: Troubleshooting In-App Messaging
solution: Marketing Cloud,Analytics
title: Troubleshooting In-App Messaging
topic: Metrics
uuid: 39c3a21d-92c2-4004-b00f-99b6f91d3696
---

# Troubleshooting In-App Messaging{#troubleshooting-in-app-messaging}

This information helps you troubleshoot in-app messaging.

 If you have completed all the requirements for In-App Messaging, but messages do not display, check the following items: 

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
   <td colname="col2"> <p>Verify that the SDK is version 4.2 or higher and is correctly configured. For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/mobile/bloodhound/view_hits.html" format="https" scope="external"> View Hits</a> for a screen shot showing the SDK version. </p> <p>Ensure that you have a <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/messaging.html" format="https" scope="external"> Messages</a> section in your configuration (downloaded JSON file), or have a Messages remote endpoint, so that it can be retrieved from dynamic tag management. </p> <p> <p>Important:  As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> My full screen message in Android is not showing up. I am using the correct SDK, configuration, and my triggers are being met. </p> </td> 
   <td colname="col2"> <p> Did you update your manifest file to define the full screen activity? </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> My local notification message in Android is not working. </p> </td> 
   <td colname="col2"> <p> Ensure that the local notification broadcast receiver is declared in your manifest. </p> <p>For more information, see step 2 in <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/messaging.html" format="https" scope="external"> Enabling In-App Messaging</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Is the message live? </p> </td> 
   <td colname="col2"> <p>To verify whether your message is live, on the <span class="wintitle"> Manage In-App Message</span> page, in the <span class="uicontrol"> Status</span> column, check the list of messages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Double check the traits/trigger sections. </p> </td> 
   <td colname="col2"> <p> Verify the assumptions in data for traits/trigger in Bloodhound. </p> <p>Validate the hits in Bloodhound. For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/mobile/bloodhound/view_hits.html" format="https" scope="external"> View Hits</a> in Bloodhound documentation for a screen shot that displays the SDK version. </p> <p> <p>Important:  As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Look at <span class="term"> show once</span>, <span class="term"> show always</span>, <span class="term"> show offline</span> settings on the Audience tab. </p> </td> 
   <td colname="col2"> <p> Verify that these settings are set the way you want. On the <span class="uicontrol"> Audience</span> tab, review your <span class="uicontrol"> Trigger</span> options, which allow you to specify how often the message is shown. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> If using launch event as trigger... </p> </td> 
   <td colname="col2"> <p> Launch only fires on a new session. For more information about when a session begins, see the <span class="codeph"> lifecycleTimeout</span> row in <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/json_config.html" format="https" scope="external"> JSON Config</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> I updated my message remotely, but my app is still showing the old message. </p> </td> 
   <td colname="col2"> <p>Complete one of the following tasks: </p> <p> 
     <ul id="ul_F9F1B9500C8E45D2A7A37905F149B820"> 
      <li id="li_6A6CB4C5B5354B038EA9A347620FDBA0">Dynamic tag management can take a few minutes to update its endpoint with your new definition. <p>Wait for some time and try again. </p> </li> 
      <li id="li_CF3FBFE18C724BCBA9A0C23F03877575">The config will only update on a new launch. <p>If the app was restarted during the life cycle session timeout, your new config might not have been downloaded. </p> </li> 
     </ul> </p> <p>For more information, see <a href="../../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>My image does not fit exactly into the space provided by the template. </p> </td> 
   <td colname="col2"> <p>The In-App Message full-screen template supports displaying an image from a remote server (Image URL) or from the app bundle (Bundled Image). The image should be in a standard image format, such as JPG, GIF or PNG. </p> <p>Because device screens have many different dimensions, the image will most likely not fit exactly into the space provided by the template. The template focuses on showing the center of the image and, if the image does not fit, crops (portrait) or fades (landscape) the sides. </p> <p>Here is the exact placement and sizing rules for each orientation: </p> <p> 
     <ul id="ul_271EE431B7BE4DC7A22D4B6A4B0218D6"> 
      <li id="li_AFCACA75BFA04CBC8D7505D426E24051"> <p><b>Portrait</b> </p> 
       <ul id="ul_A722B22DF73D4D439012508871A1897D"> 
        <li id="li_308B92BEAA8E4857BD79221E0F51046F"> <p>A height of 195px for phones </p> </li> 
        <li id="li_D1E4F4E36E224F759676E8D7CDD068F7"> <p>A height of 529px for tablets </p> </li> 
        <li id="li_B59CAC79DF7040399529E857F3FDD590"> <p>Centered if the image width is smaller than the device width. </p> </li> 
        <li id="li_B33E404F65774536AB1DE75D5D191AD1"> <p>Cropped if the image width is greater than the device width. </p> </li> 
       </ul> </li> 
      <li id="li_DE892D0C39284328A2989ACB0C6E9E64"> <p><b>Landscape</b> </p> 
       <ul id="ul_ACACD99B50374A8988C10576C0F6CD69"> 
        <li id="li_2B75165DD9E64F2C92D0F2620538ED68">The image scaled to 100% of the height of the device. </li> 
        <li id="li_F575868A78FC47B28F3A95CB492EACD6">The width is 75% of the device, with a fade out on the right. </li> 
       </ul> </li> 
     </ul> </p> <p>If you have issues with the full-screen template, you can download and use the Custom HTML template. This template provides more flexibility for images and allows full control of the template. </p> </td> 
  </tr> 
 </tbody> 
</table>

