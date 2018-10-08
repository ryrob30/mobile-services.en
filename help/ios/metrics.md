---
description: The following tables list the metrics and dimensions that can be automatically measured by the mobile library after lifecycle is implemented.
seo-description: The following tables list the metrics and dimensions that can be automatically measured by the mobile library after lifecycle is implemented.
seo-title: Lifecycle Metrics
solution: Marketing Cloud,Analytics
title: Lifecycle Metrics
topic: Developer and implementation
uuid: 29ad2238-0613-4369-88fc-c0fbb356bf9c
index: y
internal: n
snippet: y
translate: y
---

# Lifecycle Metrics

The following tables list the metrics and dimensions that can be automatically measured by the mobile library after lifecycle is implemented.

This topic contains the following information:

* [Lifecycle Metrics and Dimensions](metrics.md#section_78F036C4296F4BA3A47C2044F79C86C1) 
* [Additional Mobile Metrics and Dimensions](metrics.md#section_0B32BBF9CA734103BEDB5E755FFE5B31)

## Lifecycle Metrics and Dimensions {#section_78F036C4296F4BA3A47C2044F79C86C1}

After lifecycle metrics are configured, the metrics are sent in context data parameters to [!DNL Analytics], parameters to [!DNL Target] with each mbox call, and as a signal to [!DNL Audience Manager]. [!DNL Analytics] and [!DNL Target] use the same format, while [!DNL Audience Manager] uses a different prefix for each metric.

For [!DNL Analytics], the context data that is sent with each lifecycle tracking call is automatically captured in and reported by using the metric or dimension that listed in the first column.

>[!TIP]
>
>Exceptions are provided in the **[!UICONTROL Description]** column.

**Metrics**

<table id="table_953334C153F9490ABDB5174E26572C47"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> <p>Metric </p> </th> 
   <th colname="col02" class="entry"> <p>Analytics Context Data/Target Parameter </p> </th> 
   <th colname="col4" class="entry"> <p>Audience Manager Signal </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p> First Launches </p> </td> 
   <td colname="col02"> <p>a.InstallEvent </p> </td> 
   <td colname="col4"> <p>c_a_InstallEvent </p> </td> 
   <td colname="col2"> <p>Triggered at the first run after installation or re-installation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Upgrades </p> </td> 
   <td colname="col02"> <p>a.UpgradeEvent </p> </td> 
   <td colname="col4"> <p>c_a_UpgradeEvent </p> </td> 
   <td colname="col2"> <p>Triggered at the first run after upgrade or anytime the version number changes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Daily Engaged Users </p> </td> 
   <td colname="col02"> <p>a.DailyEngUserEvent </p> </td> 
   <td colname="col4"> <p>c_a_DailyEngUserEvent </p> </td> 
   <td colname="col2"> <p>Triggered when the application is used on a particular day. </p> <p>Important:  This metric is not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture this metric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Monthly Engaged Users </p> </td> 
   <td colname="col02"> <p>a.MonthlyEngUserEvent </p> </td> 
   <td colname="col4"> <p>c_a_MonthlyEngUserEvent </p> </td> 
   <td colname="col2"> <p>Triggered when the application is used during a particular month. </p> <p>Important:  This metric is not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture this metric. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Launches </p> </td> 
   <td colname="col02"> <p>a.LaunchEvent </p> </td> 
   <td colname="col4"> <p>c_a_LaunchEvent </p> </td> 
   <td colname="col2"> <p>Triggered on every run, including crashes and installs. Also triggered when the app is resumed from the background after the lifecycle session timeout is exceeded. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Crashes </p> </td> 
   <td colname="col02"> <p>a.CrashEvent </p> </td> 
   <td colname="col4"> <p>c_a_CrashEvent </p> </td> 
   <td colname="col2"> <p>Triggered when the application is not backgrounded before closing. The event is sent when the application is started again after the crash. </p> <p>Adobe Mobile crash reporting does not implement a global uncaught exception handler. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Previous Session Length </p> </td> 
   <td colname="col02"> <p>a.PrevSessionLength </p> </td> 
   <td colname="col4"> <p>c_a_PrevSessionLength </p> </td> 
   <td colname="col2"> <p>Reports the number of seconds that a previous application session lasted based on how long the application was open and in the foreground. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Dimensions**

<table id="table_2F24CB1C8E8448AE9A94D3AD57C21662"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Dimension </p> </th> 
   <th colname="col02" class="entry"> <p>Analytics Context Data/Target </p> </th> 
   <th colname="col4" class="entry"> <p>Audience Management </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Install Date </p> </td> 
   <td colname="col02"> <p>a.InstallDate </p> </td> 
   <td colname="col4"> <p>c_a_InstallDate </p> </td> 
   <td colname="col3"> <p>Date of first launch after installation. <span class="codeph"> MM/DD/YYYY</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> App ID </p> </td> 
   <td colname="col02"> <p>a.AppID </p> </td> 
   <td colname="col4"> <p>c_a_AppID </p> </td> 
   <td colname="col3"> <p>Stores the Application name and version in the following format: </p> <p> <span class="codeph"> [AppName] [BundleVersion] </span> </p> <p>For example, <span class="codeph"> myapp 1.1</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Launch Number </p> </td> 
   <td colname="col02"> <p>a.Launches </p> </td> 
   <td colname="col4"> <p>c_a_Launches </p> </td> 
   <td colname="col3"> <p>Number of times the application was launched or brought out of the background. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Days since first use </p> </td> 
   <td colname="col02"> <p>a.DaysSinceFirstUse </p> </td> 
   <td colname="col4"> <p>c_a_DaysSinceFirstUse </p> </td> 
   <td colname="col3"> <p>Number of days since first run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Days since last use </p> </td> 
   <td colname="col02"> <p>a.DaysSinceLastUse </p> </td> 
   <td colname="col4"> <p>c_a_DaysSinceLastUse </p> </td> 
   <td colname="col3"> <p>Number of days since last use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Hour of Day </p> </td> 
   <td colname="col02"> <p>a.HourOfDay </p> </td> 
   <td colname="col4"> <p>c_a_HourOfDay </p> </td> 
   <td colname="col3"> <p>Measures the hour the app was launched and uses the 24-hour numerical format. Used for time parting to determine peak usage times. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Day of Week </p> </td> 
   <td colname="col02"> <p>a.DayOfWeek </p> </td> 
   <td colname="col4"> <p>c_a_DayOfWeek </p> </td> 
   <td colname="col3"> <p>Number of the week day the app was launched. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Operating System Version </p> </td> 
   <td colname="col02"> <p>a.OSVersion </p> </td> 
   <td colname="col4"> <p>c_a_OSVersion </p> </td> 
   <td colname="col3"> <p>OS version. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Days since last upgrade </p> </td> 
   <td colname="col02"> <p>a.DaysSinceLastUpgrade </p> </td> 
   <td colname="col4"> <p>c_a_DaysSinceLastUpgrade </p> </td> 
   <td colname="col3"> <p>Number of days since the application version number has changed. </p> <p>Important:  This metric is not automatically stored in an Analytics variable. You must create a processing rule to copy this value to an Analytics variable for reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Launches since last upgrade </p> </td> 
   <td colname="col02"> <p>a.LaunchesSinceUpgrade </p> </td> 
   <td colname="col4"> <p>c_a_LaunchesSinceUpgrade </p> </td> 
   <td colname="col3"> <p>Number of launches since the application version number has changed. </p> <p>Important:  This metric is not automatically stored in an Analytics variable. You must create a processing rule to copy this value to an Analytics variable for reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Device Name </p> </td> 
   <td colname="col02"> <p>a.DeviceName </p> </td> 
   <td colname="col4"> <p>c_a_DeviceName </p> </td> 
   <td colname="col3"> <p>Stores the device name. </p> <p>Comma-separated two-digit string that identifies the iOS device. The first number typically represents the device generation, and the second number typically versions different members of the device family. For a list of common device names, see <a href="reference/device_versions.md#concept_3E692676526448D58DFD69388EA0E34E" format="dita" scope="local"> iOS Device Versions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carrier Name </p> </td> 
   <td colname="col02"> <p>a.CarrierName </p> </td> 
   <td colname="col4"> <p>c_a_CarrierName </p> </td> 
   <td colname="col3"> <p>Stores the name of the mobile service provider as provided by the device. </p> <p>Important:  This metric is not automatically stored in an Analytics variable. You must create a processing rule to copy this value to an Analytics variable for reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Resolution </p> </td> 
   <td colname="col02"> <p>a.Resolution </p> </td> 
   <td colname="col4"> <p>c_a_Resolution </p> </td> 
   <td colname="col3"> <p> Width x Height in actual pixels. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Additional Mobile Metrics and Dimensions {#section_0B32BBF9CA734103BEDB5E755FFE5B31}

The following metrics and dimensions are captured in mobile solution variables by the method listed in the **Description** column.

**Metrics**

<table id="table_92CBE8E17335426691B77B462E4BCA6F"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> <p>Event </p> </th> 
   <th colname="col02" class="entry"> <p>Analytics Context Data/Target Parameter </p> </th> 
   <th colname="col4" class="entry"> <p>Audience Management Trait </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> Action Time Total </td> 
   <td colname="col02"> a.action.time.total </td> 
   <td colname="col4"> c_a_action_time_total </td> 
   <td colname="col2"> <p>Populated by <span class="codeph"> trackTimedAction</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> Action Time In App </td> 
   <td colname="col02"> a.action.time.inapp </td> 
   <td colname="col4"> c_a_action_time_inapp </td> 
   <td colname="col2"> <p>Populated by <span class="codeph"> trackTimedAction</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> Lifetime Value (event) </td> 
   <td colname="col02"> a.ltv.amount </td> 
   <td colname="col4"> c_a_ltv_amount </td> 
   <td colname="col2"> <p>Populated by <span class="codeph"> trackLifetimeValue</span> methods. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Dimensions**

<table id="table_8986A9AD2C1541E1870CCE493EAC124C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Dimension </p> </th> 
   <th colname="col02" class="entry"> <p>Analytics Context Data/Target Parameter </p> </th> 
   <th colname="col4" class="entry"> <p>Audience Management Trait </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Location (down to 10 km) </td> 
   <td colname="col02"> <p>a.loc.lat.a </p> <p>a.loc.lon.a </p> </td> 
   <td colname="col4"> <p>c_a_loc_lat_a </p> <p>c_a_loc_lon_a </p> </td> 
   <td colname="col3"> <p>Populated by <span class="codeph"> trackLocation</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Location (down to 100 m) </td> 
   <td colname="col02"> <p>a.loc.lat.b </p> <p>a.loc.lon.b </p> </td> 
   <td colname="col4"> <p>c_a_loc_lat_b </p> <p>c_a_loc_lon_b </p> </td> 
   <td colname="col3"> <p>Populated by <span class="codeph"> trackLocation</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Location (down to 1 m) </td> 
   <td colname="col02"> <p>a.loc.lat.c </p> <p>a.loc.lon.c </p> </td> 
   <td colname="col4"> <p>c_a_loc_lat_c </p> <p>c_a_loc_lon_c </p> </td> 
   <td colname="col3"> <p>Populated by <span class="codeph"> trackLocation</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Point of Interest Name </td> 
   <td colname="col02"> a.loc.poi </td> 
   <td colname="col4"> c_a_loc_poi </td> 
   <td colname="col3"> <p>Populated by <span class="codeph"> trackLocation</span> methods when device is in a defined POI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Distance to Point of Interest Center </td> 
   <td colname="col02"> a.loc.dist </td> 
   <td colname="col4"> c_a_loc_dist </td> 
   <td colname="col3"> <p>Populated by <span class="codeph"> trackLocation</span> methods when device is in a defined POI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lifetime Value (conversion variable) </td> 
   <td colname="col02"> a.ltv.amount </td> 
   <td colname="col4"> c_a_ltv_amount </td> 
   <td colname="col3"> <p>Populated by <span class="codeph"> trackLifetimeValue</span> methods. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tracking Code </p> </td> 
   <td colname="col02"> a.referrer.campaign.trackingcode </td> 
   <td colname="col4"> c_a_referrer_campaign_trackingcode </td> 
   <td colname="col3"> <p>Populated by Mobile App Acquisition. Generated automatically by Adobe mobile services. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign </p> </td> 
   <td colname="col02"> a.referrer.campaign.name </td> 
   <td colname="col4"> c_a_referrer_campaign_name </td> 
   <td colname="col3"> <p>Name of the campaign, also stored in the <span class="varname"> campaign</span> variable. Populated by Mobile App Acquisition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign Content </p> </td> 
   <td colname="col02"> a.referrer.campaign.content </td> 
   <td colname="col4"> c_a_referrer_campaign_content </td> 
   <td colname="col3"> <p>The name or ID of the content that displayed the link. Populated by Mobile App Acquisition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign Medium </p> </td> 
   <td colname="col02"> a.referrer.campaign.medium </td> 
   <td colname="col4"> c_a_referrer_campaign_medium </td> 
   <td colname="col3"> <p>Marketing medium, such as banner or email. Populated by Mobile App Acquisition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Campaign Source </p> </td> 
   <td colname="col02"> a.referrer.campaign.source </td> 
   <td colname="col4"> c_a_referrer_campaign_source </td> 
   <td colname="col3"> <p>Original referrer, such as newsletter or social media network. Populated by Mobile App Acquisition. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaign Term </p> </td> 
   <td colname="col02"> a.referrer.campaign.term </td> 
   <td colname="col4"> c_a_referrer_campaign_term </td> 
   <td colname="col3"> <p>Paid keywords or other terms you want to track with this acquisition. Populated by Mobile App Acquisition. </p> </td> 
  </tr> 
 </tbody> 
</table>

