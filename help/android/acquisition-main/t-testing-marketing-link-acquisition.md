---
description: The following instructions help you roundtrip an acquisition campaign with a marketing link on an Android device.
keywords: android;library;mobile;sdk
seo-description: The following instructions help you roundtrip an acquisition campaign with a marketing link on an Android device.
seo-title: Testing Marketing Link Acquisition
solution: Marketing Cloud,Analytics
title: Testing Marketing Link Acquisition
topic: Developer and implementation
uuid: d0933dcc-8fc3-4f60-987f-7a54559aacf5
index: y
internal: n
snippet: y
---

# Testing Marketing Link Acquisition{#testing-marketing-link-acquisition}

The following instructions help you roundtrip an acquisition campaign with a marketing link on an Android device.

If your mobile app is not yet in Google Play, you can select any mobile app as a destination when creating the marketing link. This only affects the app to which the acquisition server redirects you, after you click the acquisition link, and not the ability to test the acquisition link. Query string parameters are passed to the Google Play store, which are passed to the app at install as part of a campaign broadcast. Roundtrip mobile app acquisition testing requires the simulation of this type of broadcast.

The app must be freshly installed, or have data cleared in **[!UICONTROL Settings]**, each time a test is run. This ensures that the initial lifecycle metrics that are associated with the campaign query string parameters are sent when the app is first launched. 

1. Complete the prerequisite tasks in [Mobile App Acquisition](../acquisition-main/acquisition.md#concept_ADB7BFDDBE9B4FFC8DD4940F49E2F0FA) and ensure that you have correctly implemented the broadcast receiver for `INSTALL_REFERRER`.
1. In the [!DNL Adobe Mobile Services] UI, click  **[!UICONTROL Acquisition]** > **[!UICONTROL Marketing Links Builder]** and generate an acquisition marketing link URL that sets Google Play as the destination for Android devices.

   For more information, see [Marketing Links Builder](https://marketing.adobe.com/resources/help/en_US/mobile/index.html?f=c_marketing-links-builder).

   For example:

   ```
   https://c00.adobe.com/v3/da120731d6c09658b82d8fac78da1d5fc2d09c48e21b3a55f9e2d7344e08425d/start?a_dl=573e5bb3248a501360c2890b
   ```

1. Open the generated link on the Android device.

   You should be redirected to a page with a URL similar to the following example:

   ```
   https://play.google.com/store/apps/details?id=com.adobe.android&referrer=utm_campaign%3Dadb_acq_v3%26utm_source%3Dadb_acq_v3%26utm_content%3D91b52ce097b1464b9b47cb2995c493cc6ab2c3a3
   ```

1. Copy the unique ID after `utm_content%3D`.

   In the previous example, the ID is `91b52ce097b1464b9b47cb2995c493cc6ab2c3a3`.

   If you cannot get the unique ID on the device, run the following `CURL` command on your desktop to get the unique ID from the response string.

   ```
   curl -A "Mozilla/5.0 (Linux; Android 5.0.2; SAMSUNG SM-T815Y Build/LRX22G) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/44.0.2403.133 Safari/537.36" <Your Marketing Link>
   ```

   For example:

   ```
   curl -A "Mozilla/5.0 (Linux; Android 5.0.2; SAMSUNG SM-T815Y Build/LRX22G) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/44.0.2403.133 Safari/537.36" https://c00.adobe.com/v3/da120731d6c09658b82d8fac78da1d5fc2d09c48e21b3a55f9e2d7344e08425d/start?a_dl=573e5bb3248a501360c2890b
   ```

1. Construct the acquisition end link by using the unique ID from step 3, by using the following format:

   ```
   https://c00.adobe.com/v3/<appid>/end?a_ugid=<unique id>
   ```

   For example:

   ```
   https://c00.adobe.com/v3/<appid>/end?a_ugid=91b52ce097b1464b9b47cb2995c493cc6ab2c3a3
   ```

1. Open the link in a browser.

   You should be see the `contextData` in the JSON response:

   ```
   {"fingerprint":"44b2f88a062df7e727c047f006deb9971304617b","endCallbacks":["***"],"timestamp":1464301282,"appguid":"da120731d6c09658b82d8fac78da1d5fc2d09c48e21b3a55f9e2d7344e08425d","contextData": 
   {"a.launch.campaign.trackingcode":"trymttvm","a.referrer.campaign.name":"Android Demo","a.referrer.campaign.trackingcode":"trymttvm"} 
   ,"adobeData":{"unique_id":"9a2be52764a8db125c29a8c10f3b1b3d5d8ed915","deeplinkid":"57476c26072932ec6d3a470b"}}.
   ```

1. Repeat step 3 to get a new unique ID.
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
      <td colname="col2"> <p>The server should be <span class="filepath"> c00.adobe.com </span> </p> <p> <span class="codeph"> appid </span> should equal the &lt;appid&gt; in your acquisition link </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>analytics </p> </td> 
      <td colname="col2"> <p>For testing purposes, set the referrer timeout to allow for adequate time (60 seconds or more) to manually send the broadcast. You can restore the original timeout setting after testing. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Connect the device to a computer, uninstall, and install the app again.
1. Launch ADB Shell and launch the application on the device.

   ```
   adb shell
   ```

1. Send a broadcast by using the following `adb` command:

   ```
   am broadcast -a com.android.vending.INSTALL_REFERRER -n com.adobe.android/com.adobe.android.YourBroadcastReceiver --es "referrer" "utm_source=adb_acq_v3&utm_campaign=adb_acq_v3&utm_content=<unique id get on step 5>"
   ```

1. Replace [!DNL com.adobe.android] with your application's package name, update the receiver reference with the reference of the location of the campaign tracking receiver in your app, and replace the values that are associated with [!DNL utm_content].

   If the broadcast is successful, you should expect a response like the following example:

   ```
   Broadcasting: Intent 
   { act=com.android.vending.INSTALL_REFERRER cmp=com.adobe.adms.tests/.ReferralReceiver (has extras) } 
   Broadcast completed: result=0 
   
   ```

1. (Optional) You can enable debug logging of the SDK to obtain additional information.

   If everything works correctly, you should see following logs:

   ```
   "Analytics - Received referrer information(<referrer content>)" 
   "Analytics - Trying to fetch referrer data from (acquisition end url)"; 
   "Analytics - Received Referrer Data(<A JSON Response>)"
   ```

   If you do not see these logs, verify that you have completed performed steps 6 to 10.

   The following table contains additional information about the possible errors: 

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
          Analytics - Unable to decode response(&lt;String&gt;). 
        </msgph> </p> </td> 
      <td colname="col2"> <p>The response is malformed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 
        <msgph>
          Analytics - Unable to parse response(&lt;A JSON Response&gt;. 
        </msgph> </p> </td> 
      <td colname="col2"> <p>The JSON string is malformed. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 
        <msgph>
          Analytics - Unable to parse acquisition service response (no contextData parameter in response). 
        </msgph> </p> </td> 
      <td colname="col2"> <p>There in no <span class="codeph"> contextData </span> parameter in the response. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 
        <msgph>
          Analytics - Acquisition referrer data was not complete (no a.referrer.campaign.name in context data), ignoring. 
        </msgph> </p> </td> 
      <td colname="col2"> <p> <span class="codeph"> a.referrer.campaign.name </span> is not included in <span class="codeph"> contextData </span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p> 
        <msgph>
          Analytics - Acquisition referrer timed out. 
        </msgph> </p> </td> 
      <td colname="col2"> <p>Failed to get the response in the time defined by <span class="codeph"> referrerTimeout </span>. Increase the value and try again. </p> <p>You should also ensure that you've opened the acquisition link before installing the app. </p> </td> 
      </tr> 
    </tbody> 
    </table>

Remember the following information: 

* Hits that are sent from the app can be monitored by using HTTP monitoring tools to verify the acquisition attribution. 
* For more information about how to broadcast `INSTALL_REFERRER`, see [Testing Google Play Campaign Measurement](https://developers.google.com/analytics/solutions/testing-play-campaigns) in the Google Developers guide . 
* You can use the provided [!DNL acquisitionTest.jar] Java tool to help you get the unique ID and broadcast install referrer, which in turn, helps you obtain the information in steps 3 to 10. 

  **Install the Java Tool** 

  To install the Java tool:
    1. Download the `acquistionTester.zip` file. 
    1. Extract the .jar file. 

  You can run the .jar file on the command line. 

  For example: 

  ```
  java -jar acquisitionTester.jar -a com.adobe.test -r com.adobe.test.ReferrerReceiver -l "https://c00.adobe.com/v3/appid/start?a_i_id=123456&a_g_id=com.adobe.test&a_dd=i&ctxa.referrer.campaign.name=name&ctxa.referrer.campaign.trackingcode=1234
  ```

* The marketing links are cached on the server side with a ten-minutes expiration time. 

  When you make changes to marking links, wait about 10 minutes before the changes take effect before you use the links again. 

