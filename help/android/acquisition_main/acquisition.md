---
description: Acquisition links with unique tracking codes can be generated in Adobe Mobile services. When a user downloads and runs an app from the app store after clicking on the generated link, the SDK automatically collects and sends the acquisition data to Adobe Mobile services.
keywords: android;library;mobile;sdk
seo-description: Acquisition links with unique tracking codes can be generated in Adobe Mobile services. When a user downloads and runs an app from the app store after clicking on the generated link, the SDK automatically collects and sends the acquisition data to Adobe Mobile services.
seo-title: Mobile App Acquisition
solution: Marketing Cloud,Analytics
title: Mobile App Acquisition
topic: Developer and implementation
uuid: 30a015c1-ecba-4843-9c2a-4b541f97b98b
index: y
internal: n
snippet: y
translate: y
---

# Mobile App Acquisition


>[!IMPORTANT]
>
>To use Acquisition, you**must** have SDK version 4.1 or later. 



Acquisition links must be created in Adobe Mobile services. For more information, see [ App Acquisition Analytics ](https://marketing.adobe.com/resources/help/en_US/mobile/?f=acquisition). 

**In SDK versions 4.13.1 and later**: 

If you cannot use the acquisition links that are created in [!DNL  Adobe Mobile Services], the acquisition data can still be collected and sent by the SDK by using Google Play Acquisition. 

To collect acquisition data from a standard Google Play Acquisition campaign: 


* Use the standard Google Play Store acquisition method. Custom acquisition data can be used with the standard Google Play Acquisition key value pairs. 

* When the user downloads and runs an app as the result of a Google Play store acquisition, the data from the referrer will be collected and sent to [!DNL  Adobe Mobile Services]. 
    * The data will be stored and available in the ` AdobeDataCallback` instance that was registered earlier with the SDK. For more information, see [ Configuration Methods ](../configuration/methods.md#concept_12F12E3E0E434F8CB997AF4027810EBF). 

    * The ` MobileDataEvent.MOBILE_EVENT_ACQUISITION_INSTALL` or the ` MobileDataEvent.MOBILE_EVENT_ACQUISITION_LAUNCH` event type will be used. For more information, see [ MobileDataEvent Enum ](../configuration/methods.md#section_92732814141646E294782BC9020367EB). 

    * Custom keys that were part of the acquisition data from Google Play will be name-spaced with " ` a.acquisition.custom.`"




If you are using the Acquisition links that were created on [!DNL  Adobe Mobile Services], add custom data to the acquisition link by completing the following tasks: 


1. Prefix an acquisition variable with " ` adb`". When the SDK receives the acquisition data from [!DNL  Adobe Mobile Services] (on first launch), that data will be stored and also available in the ` AdobeDataCallback` instance registered earlier with the SDK, as mentioned in [ Configuration Methods ](../configuration/methods.md#concept_12F12E3E0E434F8CB997AF4027810EBF). 

1. The ` MobileDataEvent.MOBILE_EVENT_ACQUISITION_INSTALL` or the ` MobileDataEvent.MOBILE_EVENT_ACQUISITION_LAUNCH` event type will be used.
1. The custom data keys will be prefixed with " ` a.acquisition.custom.`"


>[!TIP]
>
>If you are sending data to multiple report suites, use the acquisition data from the app that is associated with the first report suite in your list of report suite IDs.

The updates in this section enable the SDK to send acquisition data from an acquisition link. 

## Tracking Mobile Acquisition {#section_CEA30C652AC8470784B8054E299B80FA}


1. Add the library [ to your project and implement lifecycle ](../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972). 

1. Import the library: 
   ```
   java   import com.adobe.mobile.*;
   ```


1. Implement the ` BroadcastReceiver` for the referrer: 
   ```
   java   package com.your.package.name;  // replace with your app package name 
    
   import android.content.BroadcastReceiver; 
   import android.content.Context; 
   import android.content.Intent; 
    
   public class GPBroadcastReceiver extends BroadcastReceiver { 
     @Override 
     public void onReceive(Context c, Intent i) { 
      com.adobe.mobile.Analytics.processReferrer(c, i); 
     } 
   }
   ```


1. Update ` AndroidManifest.xml` to enable the ` BroadcastReceiver` that was created in the previous step: 
   ```
   xml   <receiver android:name="com.your.package.name.GPBroadcastReceiver" android:exported="true"> 
    <intent-filter> 
     <action android:name="com.android.vending.INSTALL_REFERRER" /> 
    </intent-filter> 
   </receiver>
   ```


1. Verify that ` ADBMobileConfig.json` contains the required acquisition settings: 
   ```
   xml   "acquisition": { 
      "server": "c00.adobe.com", 
      "appid": "0652024f-adcd-49f9-9bd7-2552a4565d2f" 
   }, 
   "analytics": { 
     "referrerTimeout": 5, 
     ...
   ```


   >[!IMPORTANT]
   >
   >If you are sending data to multiple report suites, use the acquisition settings (acquisition server and appid) from the app that is associated with the first report suite in your list of report suite IDs.
   The ` acquisition` settings are generated by [ Adobe Mobile services ](https://mobilemarketing.adobe.com) and should not be changed. For more information about how to download a customized ` ADBMobileConfig.json` file with the ` acquisition` settings pre-configured, see [ Before You Start ](../getting_started/requirements.md#concept_2FA4E790CA1646FFB44488CF017821DE). 



After these settings are enabled, after the initial launch of the app, acquisition data is sent automatically with the initial lifecycle call. 

>[!CAUTION]
>
>` referrerTimeout` must be set to a value higher than 0 to enable app acquisition. 

