---
description: Acquisition tracking must be enabled in the SDK configuration before you can track and report on marketing links.
keywords: mobile
seo-description: Acquisition tracking must be enabled in the SDK configuration before you can track and report on marketing links.
seo-title: Configure Acquisition
solution: Marketing Cloud,Analytics
title: Configure Acquisition
topic: Metrics
uuid: c9b31f32-546b-4100-b72d-5d25a5646947
index: y
internal: n
snippet: y
translate: y
---

# Configure Acquisition


>1. On the [!UICONTROL  Manage App Settings] page for the app, scroll to the **[!UICONTROL  SDK Acquisition Options]** section.
>1. Complete the following tasks:


>    <table id="table_1E195F21EE08487C8435CB3C43040A9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> UI item </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Enable </span> check box </p> </td> 
   <td colname="col2"> <p>To enable acquisition, select the check box. </p> <p>When you select this check box, the <span class="uicontrol"> Referrer Timeout</span> field becomes active, and the value changes from <span class="uicontrol"> 0</span> to <span class="uicontrol"> 5</span> seconds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Referrer Timeout (seconds)</span> field </p> </td> 
   <td colname="col2"> <p>(Optional) This field is optional if you have already enabled the <span class="uicontrol"> Enable</span> check box. </p> <p>You can change the timeout value, which is specified in seconds. This setting specifies the time to wait for acquisition information before sending the First Launch hit. We recommend that you use the five-second default value. </p> <p> <p type="important">Note:  This value must be a non-zero value. If you enable acquisition but leave the value s zero, the acquisition links will not function. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>1. Download and use the new SDK configuration file in your app.

>       **iOS**1. To enable Acquisition on **Android**, complete the steps in *Tracking Mobile Acquisition* in [ Mobile App Acquisition](https://marketing.adobe.com/resources/help/en_US/mobile/android/acquisition.html).
