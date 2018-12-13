---
description: This information helps you roundtrip a V3 acquisition campaign link based on a device fingerprint.
seo-description: This information helps you roundtrip a V3 acquisition campaign link based on a device fingerprint.
seo-title: Testing V3 Acquisition
solution: Marketing Cloud,Analytics
title: Testing V3 Acquisition
uuid: 89137ccf-4839-4b37-926e-303cf8e511a5
index: y
internal: n
snippet: y
---

# Testing V3 Acquisition{#testing-v-acquisition}

This information helps you roundtrip a V3 acquisition campaign link based on a device fingerprint.

>[!IMPORTANT]
>
>V3 Acquisition refers to the acquisition links that you create with the [!DNL Acquisition Builder] in the [!DNL Adobe Mobile Services] UI. To use this feature, you must upgrade to iOS SDK version 4.6.0 or later.

If the mobile app is not yet in the App Store, when you create the campaign link, select any mobile app as a destination. This only affects the app to which the acquisition server redirects you after you click the acquisition link, but does not affect the ability to test the link. 

1. Complete the prerequisite tasks in [Mobile App Acquisition](../acquisition-main/acquisition.md#concept_ADB7BFDDBE9B4FFC8DD4940F49E2F0FA).
1. Navigate to the **[!UICONTROL Acquisition Builder]** in the [!DNL Adobe Mobile Services] UI and generate an acquisition campaign URL.

   For example:

   ```
   https://c00.adobe.com/v3/<appid>/start?a_i_id=iostestapp&a_g_id=com.adobe.android&a_dd=i&ctxa.referrer.campaign.name=name&ctxa.referrer.campaign.trackingcode=trackingcode
   ```

   If you refer to both iOS and Android apps in the acquisition link, use the Apple Store as the default store. 
1. Open the generated link in a desktop browser and go to [!DNL `https://c00.adobe.com/v3/<appid>/end`].

   You should see the `contextData` in the JSON response:

   ```
   {"fingerprint":"228d7e6058b1d731dc7a8b8bd0c15e1d78242f31","timestamp":1457989293,"appguid":"","contextData":{"a.referrer.campaign.name":"name","a.referrer.campaign.trackingcode":"trackingcode"}}.
   ```

   If you do not see contextData, or some of it is missing, ensure that the acquisition URL follows the format that is specified in [Create Acquisition Link Manually](https://marketing.adobe.com/resources/help/en_US/mobile/index.html?f=acquisition_link_manual). 
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

1. (Conditional) If the `ssl` setting in your app's config file is true, update your acquisition link to use the HTTPS protocol.
1. Click the generated link from the mobile device on which you will install the app.

   Adobe's servers ( [!DNL c00.adobe.com]) store the fingerprint and redirect to the App Store. The app does not need to be downloaded for testing. 
1. Launch the application for the first time from the same mobile device that you used in step 6.

   You can delete and install the app again, if necessary. 
1. (Optional) You can enable debug logging of the SDK to obtain additional information.

   If everything works correctly, you should see following logs:

   ```
   "Analytics - Trying to fetch referrer data from <acquisition end url>"
   "Analytics - Received Referrer Data(<Json Object>)"
   ```

   If you do not see the above logs, ensure that you have completed steps 4 and 5.

   The following table contains information to explain possible errors: 

<table id="table_9E22245A614744B38C28D7CEE4857F34"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Error </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>"Analytics - Unable to retrieve acquisition service response (&lt;error message&gt;)" </p> </td> 
   <td colname="col2"> <p>A network error occurred. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>"Analytics - Unable to parse acquisition service response (&lt;error message&gt;)" </p> </td> 
   <td colname="col2"> <p>The response is not in the correct format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>"Analytics - Unable to parse acquisition service response (no contextData parameter in response)" </p> </td> 
   <td colname="col2"> <p>There in no <span class="codeph"> contextData</span> parameter in the response. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>"Analytics - Acquisition referrer data was not complete, ignoring" </p> </td> 
   <td colname="col2"> <p><span class="codeph"> a.referrer.campaign.name</span> is not included in <span class="codeph"> contextData</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>"Analytics - Acquisition referrer timed out" </p> </td> 
   <td colname="col2"> <p>Failed to get the response in the time that is defined by <span class="codeph"> referrerTimeout</span>. Increase the value and try again. </p> <p>You should also ensure that you opened the acquisition link before installing the app and that you are using the same network when you click the URL and open the app. </p> </td> 
  </tr> 
 </tbody> 
</table>

>Remember the following information: >
>* The acquisition server provides an attribution match that is based on the IP address and user-agent information that is recorded in the link click (step 6) and when the app is launched (step 7). 
>
>  You should be on the same network when you click the URL and when you open the app. 
>
>* By using HTTP monitoring tools, hits sent from the app can be monitored to provide verification of the acquisition attribution. 
>
>  You should see one `/v3/<appid>/start` request and one `/v3/<appid>/end` request sent to the acquisition server. Variations in the user-agent sent might cause attribution to fail. 
>
>  >[!TIP]
>  >
>  >Ensure that `https://c00.adobe.com/v3/<appid>/start` and `https://c00.adobe.com/v3/<appid>/end` have the same user-agent values. 
>
>* The acquisition link and the hit from the SDK should be using the same HTTP/HTTPS protocol. 
>
>  If they are using different protocols (for example, the link uses HTTP and the SDK uses HTTPS), the IP address might differ for each request (on some carriers), and the attribution might fail. 
>
