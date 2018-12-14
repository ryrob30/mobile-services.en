---
description: You can define and configure audience options for push messages, including date range options, Analytics segments, and custom segments.
keywords: mobile
seo-description: You can define and configure audience options for push messages, including date range options, Analytics segments, and custom segments.
seo-title: Audience  Define and Configure Audience Segments for Push Messages
solution: Marketing Cloud,Analytics
title: Audience  Define and Configure Audience Segments for Push Messages
topic: Metrics
uuid: efd410e7-3b6c-4cf4-a26f-b11688adc491
index: y
internal: n
snippet: y
---

# Audience: Define and Configure Audience Segments for Push Messages{#audience-define-and-configure-audience-segments-for-push-messages}

You can define and configure audience options for push messages, including date range options, Analytics segments, and custom segments.

## Define Audience Segments {#section_7C4D2393CF7441959FE2381A02867CAC}

When an audience segment for push messaging is created, the segment might involve users from one or more apps because report suites or virtual report suites might contain data from one or more apps. For more information about virtual report suites, see [Virtual Report Suites](../../manage-apps/c-mob-vrs.md#concept_0C6EDD6139AC4B08A2316CFCE77CC717).

In Adobe Mobile Services, marketers might only push to one app per platform. If marketers attempt to push to segments that contain users from multiple apps, a warning is displayed that states that proceeding can result in serious push failures and the potential blacklisting of users. If you experience a push failure, see *Resolving push failures* in [Troubleshooting Push Messaging](../../in-app-messaging/t-create-push-message/c-troubleshooting-push-messaging.md#concept_8CECEBF5C278422796BAD09107DCED93).

To use Audience Manager data in your segment definition, see [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

>[!IMPORTANT]
>
>If app users are blacklisted, marketers can **never** send push messages to those affected users again.

If you choose an audience segment that contains users across multiple apps, you might see the following alert:

![](assets/multiple_appname.png)

The app name is based on the pared down version of the appId, which is automatically sent to Adobe Analytics by the Mobile Services SDK in the `<app name> <version number> (<bundle id>)` format.

>[!TIP]
>
>The version number is optional.

Up to 6 sets of numbers for the version and 5 sets of numbers for the bundle ID are removed.

For example:

* `Bea[rd]cons 1.0 (123)` will appear as `Bea[rd]cons` 

* `Bea[rd]cons 1.2 (1.2)` will appear as `Bea[rd]cons` 

* `Bea[rd]cons 1.2.3.4.5.6.7 (1111)` will appear as `Bea[rd]cons .7` 

* `Bea[rd]cons 1.2.3. (1.2.3.4.5.6)` will appear as `Bea[rd]cons (.6)`

To continue to send the push message to the listed apps, select the **[!UICONTROL Yes, I want to proceed.]** check box and click **[!UICONTROL Send]**.

**Best Practices**

Here are some practices to remember:

* To reduce confusion, **avoid** defining mobile app virtual report suites that contain data from multiple apps. 
* Use a unique app ID as part of an audience segment **each** time you want to send a push message.

  This ensures that push notifications are sent to an audience segment that belongs to **only** one app.

**Examples**

Here are some examples to help you understand how to correctly define segments:

**Do**: The Marketer provides push certificates for the iOS and Android versions of one app, for example, for Adobe Photoshop. The Marketer might send a push notification to a user segment that spans across both platforms.

**Do not**: Marketers provide push certificates for iOS and Android versions of one app, for example, for Adobe Photoshop. If the marketer creates and pushes to a segment of *all active users in the last 30 days*, only the users of the Adobe Photoshop iOS and Android app receive the push, and all of the Adobe Illustrator iOS and Android app users will be blacklisted. For more detailed, example see *Resolving push message failures* in [Troubleshooting Push Messaging](../../in-app-messaging/t-create-push-message/c-troubleshooting-push-messaging.md#concept_8CECEBF5C278422796BAD09107DCED93).

## Configure Audience Segments {#section_A92C60885A30421B8150820EC1CCBF13}

1. Go to the [!DNL Audience] page for a [new push message](../../in-app-messaging/t-create-push-message/t-create-push-message.md#task_70E6D9C01F5A4082B9880C049804A2A0).

   >[!IMPORTANT]
   >
   >As you configure the audience options, remember the following information: 
   >
   >
   >
   >    
   >    
   >    * The **[!UICONTROL Estimated Opt-In Audience]** is the number of devices that match the Adobe Analytics segment **and** the number of opted-in devices. 
   >    
   >    
   >      You can view an estimate of the number of users in your selected segment(s) that have opted in to receive messages and will receive the push message. The total number of app users displays below the estimate, regardless of opt-in status. 
   >    
   >    * The **[!UICONTROL Total]** is the number of devices that match the Adobe Analytics segment. 
   >    * Push messages will be sent to the devices that are part of a defined Adobe Analytics segment **and** that have opted-in for push messages. 
   >    
   >    
   >      This means that the SDK has sent a value of `True` for the Push Message Opt-In evar. 
   >    
   >    * Even though the device has a valid device token, unless Adobe Analytics has set the opted-in flag, the message will not get pushed to the device. 
   >    * For more information about troubleshooting push messaging, see the following: 
   >    
   >    
   >    
   >        
   >        
   >        * iOS: [Push Messaging](https://marketing.adobe.com/resources/help/en_US/mobile/ios/push_messaging.html) 
   >        * Android: [Push Messaging](https://marketing.adobe.com/resources/help/en_US/mobile/android/push_messaging.html) 
   >        
   >        

   >    
   >    
   >

1. Type information in the following fields:

<table id="table_13247225F51041EC8CD91BE02C9BCC2F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> During The </span> </p> </td> 
   <td colname="col2"> <p>Type the time frame to use for the estimated audience. </p> <p>From the <span class="uicontrol"> During The</span> drop-down list, select an option: </p> <p> 
     <ul id="ul_17E1C6D5ADA44E4A992567C35B0A1CE7"> 
      <li id="li_5E7BD71F96704C1FA1A215E9E2FC559C"> <p><b>Last</b> lets you select a relative time frame (for example, the last 7 days, last 30 days, or last 60 days) from the time the message is scheduled to push. </p> <p>As an example, if you select the last 30 days and schedule the message to push on October 31, the estimated audience would be the number of users who have opted-in to receive push messages the 30 days before October 31. </p> </li> 
      <li id="li_2320DCE8A02D420B9E11DAB98C154A3C"> <p><b>Static Range</b> lets you select a static range by picking the beginning and end dates for the estimated audience range. </p> <p>Using the previous example, if you select a date range beginning October 1 and ending October 15 but schedule the message to push on October 31, the estimated audience would be the number of users who have opted-in to receive push messages in the static date range that you specified (October 1 to October 15). </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Analytics Segments </span> </p> </td> 
   <td colname="col2"> <p>Select one or more existing <span class="keyword"> Adobe Analytics</span> segment from the drop-down list. </p> <p>For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html" format="https" scope="external"> Building Segments</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Custom Segments </span> </p> </td> 
   <td colname="col2"> <p>Select a metric or variable from the drop-down list (for example, <span class="uicontrol"> Days Since Last Use</span> or <span class="uicontrol"> Point of Interest</span>) and configure the filter as desired. </p> <p>For example, the following custom segment targets users who have a mobile phone running iOS and are in the California (United States) region. </p> </td> 
  </tr> 
 </tbody> 
</table>

   >[!IMPORTANT]
   >
   >In the **[!UICONTROL Create Audience]** section, if you click **[!UICONTROL And]**, a dialog box appears that reminds you to ensure that each app that is listed **must** have a valid certificate. If you clicked **[!UICONTROL Or]**, the default dialog box appears. For more information about valid certificates and report suites, see [Virtual Report Suites](../../manage-apps/c-mob-vrs.md#concept_0C6EDD6139AC4B08A2316CFCE77CC717).

