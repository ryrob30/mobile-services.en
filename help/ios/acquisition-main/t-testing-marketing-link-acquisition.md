---
description: The following instructions help you roundtrip an acquisition campaign with a marketing link that is based on a device fingerprint.
keywords: android;library;mobile;sdk
seo-description: The following instructions help you roundtrip an acquisition campaign with a marketing link that is based on a device fingerprint.
seo-title: Testing Marketing Link Acquisition
solution: Marketing Cloud,Analytics
title: Testing Marketing Link Acquisition
topic: Developer and implementation
uuid: 69503e01-182d-44c6-b0fb-e1c012ffa3bd
---

# Testing Marketing Link Acquisition{#testing-marketing-link-acquisition}

The following instructions help you roundtrip an acquisition campaign with a marketing link that is based on a device fingerprint.

1. Complete the prerequisite tasks in [Mobile App Acquisition](../acquisition-main/acquisition.md#concept_ADB7BFDDBE9B4FFC8DD4940F49E2F0FA).
1. In the [!DNL Adobe Mobile Services] UI, click **[!UICONTROL Marketing Links Builder]** and generate an acquisition marketing link URL that sets the App Store as the destination for iOS devices.

   For more information, see [Marketing Links Builder](https://marketing.adobe.com/resources/help/en_US/mobile/index.html?f=c_marketing-links-builder).

   For example:

   ```
   https://c00.adobe.com/v3/da120731d6c09658b82d8fac78da1d5fc2d09c48e21b3a55f9e2d7344e08425d/start?a_dl=57477650072932ec6d3a470f
   ```

1. Open the generated link on the iOS device and open [!DNL `https://c00.adobe.com/v3/<appid>/end`].

   You should see the contextData in the JSON response:

   ```
   {"fingerprint":"bae91bb778f0ad52e37f0892961d06ac6a5c935b","endCallbacks":["***"],"timestamp":1464301217,"appguid":"da120731d6c09658b82d8fac78da1d5fc2d09c48e21b3a55f9e2d7344e08425d","contextData":
   {"a.launch.campaign.trackingcode":"twdf4546","a.referrer.campaign.name":"iOS Demo","a.referrer.campaign.trackingcode":"twdf4546"}
   ,"adobeData":{"unique_id":"8c14098d7c79e8a180c15e4b2403549d3cc21ea8","deeplinkid":"57477650072932ec6d3a470f"}}
   
   ```

1. Verify that the following settings in your config file are correct:

<table id="table_FA9CF58B38F3437CBD39A20874335CA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Setting </th> 
   <th colname="col2" class="entry"> Value </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>acquisition </p> </td> 
   <td colname="col2"> <p>The server should be <span class="filepath"> c00.adobe.com</span> </p> <p> <span class="codeph"> appid</span> should equal the <span class="varname"> &lt;appid&gt;</span> in your acquisition link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>analytics </p> </td> 
   <td colname="col2"> <p><span class="codeph"> referrerTimeout</span> should have a value greater than 0. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Conditional) If the SSL setting in your app's config file is `false`, update your acquisition link to use the HTTP protocol instead of HTTPS.
1. Click the generated link from the mobile device on which you want to install the app.

   Adobe's servers ( [!DNL c00.adobe.com]) store the fingerprint and redirect to the App Store. The app does not need to be downloaded for testing. 
1. Launch the application for the first time from the same mobile device that you used in step 6.

   You can delete and install the app again, if necessary. 
1. (Optional) Enable debug logging of the SDK to obtain additional information.

   If everything works correctly, you should see following logs:

   ```
   "Analytics - Trying to fetch referrer data from <acquisition end url>"
   "Analytics - Received Referrer Data(<Json Object>)"
   ```

   If you do not see the above logs, verify that you completed steps 4 and 5.

   The following table contains information about possible errors: 

<table id="table_9E22245A614744B38C28D7CEE4857F34"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Error </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>
     <msgph>
       Analytics - Unable to retrieve acquisition service response (&lt;error message&gt;)
     </msgph> </p> </td> 
   <td colname="col2"> <p>A network error occurred. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>
     <msgph>
       Analytics - Unable to parse acquisition service response (&lt;error message&gt;)
     </msgph> </p> </td> 
   <td colname="col2"> <p>The response is not in the correct format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>
     <msgph>
       Analytics - Unable to parse acquisition service response (no contextData parameter in response)
     </msgph> </p> </td> 
   <td colname="col2"> <p>There is no <span class="codeph"> contextData</span> parameter in the response. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>
     <msgph>
       Analytics - Acquisition referrer data was not complete, ignoring
     </msgph> </p> </td> 
   <td colname="col2"> <p><span class="codeph"> a.referrer.campaign.name</span> is not included in <span class="codeph"> contextData</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>
     <msgph>
       Analytics - Acquisition referrer timed out
     </msgph> </p> </td> 
   <td colname="col2"> <p>Failed to get the response in the time that is defined by <span class="codeph"> referrerTimeout</span>. Increase the value and try again. </p> <p>You should also ensure that you opened the acquisition link before installing the app and that you are using the same network when you click the URL and open the app. </p> </td> 
  </tr> 
 </tbody> 
</table>

Remember the following information:

* The acquisition server provides an attribution match that based on the IP address and user-agent information that was recorded in the link click (step 6) and when the app is launched (step 7). 

  You should be on the same network when you click the URL and when you open the app. 

* By using HTTP monitoring tools, hits that are sent from the app can be monitored to provide verification of the acquisition attribution. 

  You should see one `/v3/<appid>/start` request and one `/v3/<appid>/end` request that are sent to the acquisition server. 

* Variations in the user-agent sent might cause attribution to fail. 

  Ensure that [!DNL `https://c00.adobe.com/v3/<appid>/start`] and [!DNL `https://c00.adobe.com/v3/<appid>/end`] have the same user-agent values. 

* The acquisition link and the hit from the SDK should be using the same HTTP/HTTPS protocol. 

  If the link and the hit are using different protocols (for example, the link uses HTTP and the SDK uses HTTPS) the IP address might differ for each request (on some carriers). This could cause the attribution to fail. 

* The marketing links are cached on the server side with a ten-minutes expiration time. 

  When you make changes to marketing links, you should wait about 10 minutes before using the links. 

