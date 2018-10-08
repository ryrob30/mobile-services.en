---
description: The following information helps you roundtrip an legacy acquisition campaign link that is based on a device fingerprint.
seo-description: The following information helps you roundtrip an legacy acquisition campaign link that is based on a device fingerprint.
seo-title: Testing Legacy Acquisition
solution: Marketing Cloud,Analytics
title: Testing Legacy Acquisition
uuid: 5cc773ee-ae32-4df8-b9dc-5d75292295fe
index: y
internal: n
snippet: y
translate: y
---

# Testing Legacy Acquisition

The following information helps you roundtrip an legacy acquisition campaign link that is based on a device fingerprint.

<!-- there is no "legacy acquisition" page in the Mobile UI. Can this topic be removed? -->

If the mobile app is not yet in Google Play, you can select any mobile app as a destination when creating the campaign link. This only affects which app the acquisition server redirects you to, after you click the acquisition link, not the ability to test the acquisition link. 

1. Navigate to [Use Legacy Acquisition Links](https://marketing.adobe.com/resources/help/en_US/mobile/index.html?f=c_use_legacy_acquisition_links) in [!DNL Adobe Mobile Services] and generate an acquisition campaign URL.
1. From the mobile device on which you will install the app, click the generated link.

   Adobe's servers ( [!DNL c00.adobe.com]) store the fingerprint and then redirect to the App Store. The app does not have to be downloaded for testing. 

1. On the same mobile device that you used in step 2, launch the application for the first time.

   The easiest way to ensure that this happens is to delete and install the app again. 

>Remember the following information: 
>
>* The acquisition server provides an attribution match that is based on IP address and user-agent information that recorded in the link click (step 2) and when the app is launched (step 3). 
>* By using HTTP monitoring tools, hits that are sent from the app can be monitored to provide verification of the acquisition attribution. 
>
>>[!TIP]
>>
>>Variations in the user-agent sent might cause attribution to fail. 
>
