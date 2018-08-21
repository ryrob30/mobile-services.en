---
description: Here is the reference information for the default mobile metrics and dimensions.
keywords: mobile
seo-description: Here is the reference information for the default mobile metrics and dimensions.
seo-title: Mobile Metrics and Dimensions Reference
solution: Marketing Cloud,Analytics
title: Mobile Metrics and Dimensions Reference
topic: Metrics
uuid: 806f41d3-d5e0-418d-9f27-0b95e39273cb
index: y
internal: n
snippet: y
translate: y
---

# Mobile Metrics and Dimensions Reference

The following sections contain more information: 

* [ Metrics](../../gs/metrics/metrics_reference.md#section_6704C815147D44AF96151D626BEB813C)
* [ Dimensions](../../gs/metrics/metrics_reference.md#section_1784C7E859F64CCEB95C5DD1DCF5C98D)

>[!TIP]
>
>The dimension and metric permissions that are set in [!DNL  Adobe Analytics] apply to [!DNL  Mobile Services]. If you attempt to run a report without proper permissions, you will receive an error. 



## Metrics {#section_6704C815147D44AF96151D626BEB813C}


<table id="table_953334C153F9490ABDB5174E26572C47"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> <p>Event </p> </th> 
   <th colname="col2" class="entry"> <p>Configuration </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p> First Launches </p> </td> 
   <td colname="col2"> <p>Triggered on the first run after an installation or a re-installation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Upgrades </p> </td> 
   <td colname="col2"> <p>Triggered on the first run after an upgrade or when the version number changes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Daily Engaged Users </p> </td> 
   <td colname="col2"> <p>Triggered when the application is used on a particular day. </p> <p> <p type="tip">Note:  The Daily Engaged Users event is not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture this metric. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Monthly Engaged Users </p> </td> 
   <td colname="col2"> <p>Triggered when the application is used during a month. </p> <p> <p type="tip">Note:  The Monthly Engaged Users event is not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture this metric. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Launches </p> </td> 
   <td colname="col2"> <p>Triggered on a run that is not an install or an upgrade. This also triggers when the application is brought out of the background. </p> <p>By default, a new launch triggers when the application is in the background for five or more minutes. The amount of background time before triggering a new launch can be configured in <span class="uicontrol"> SDK Analytics Options</span> on <span class="wintitle"> Manage App Settings</span>. For more information, see the <i>Session Timeout (Seconds)</i> row in <a href="../../c_manage_app_settings/c_mob_confg-app/t_config_analytics/t_config_analytics.md#task_8F9FBCDFB906467DAADA3FBDBBFF54CE" format="dita" scope="local"> Configure SDK Analytics Options</a>. </p> <p> <p type="important">Note: Because how visits in <span class="keyword"> Adobe Analytics</span> and mobile app launches in <span class="keyword"> Adobe Mobile Services</span> are calculated, you might see different results in reporting. For more information, see <a href="https://helpx.adobe.com/analytics/kb/compare-visits-and-mobile-app-launches.html" format="https" scope="external"> Compare Visits and Mobile App Launches</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Crashes </p> </td> 
   <td colname="col2"> <p>Triggered when the application does not correctly exit. This event is sent when the application starts after a crash. </p> <p> <p type="tip">Note:  The application is considered to crash if quit is not called. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Previous Session Length </p> </td> 
   <td colname="col2"> <p>Aggregated total Previous Session Length. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Dimensions {#section_1784C7E859F64CCEB95C5DD1DCF5C98D}


<table id="table_2F24CB1C8E8448AE9A94D3AD57C21662"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p> Dimension </p> </th> 
   <th colname="col3" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Install Date </p> </td> 
   <td colname="col3"> <p>Date of the first launch after the installation. The date is in the <span class="codeph"> MM/DD/YYYY</span> format. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> App ID </p> </td> 
   <td colname="col3"> <p>Stores the Application name and version in the following format: </p> <p> <span class="codeph"> [AppName] [BundleVersion] </span> </p> <p>For example, <span class="codeph"> myapp 1.1</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Launch Number </p> </td> 
   <td colname="col3"> <p>Number of times the application was launched or brought out of the background. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Days Since First Use </p> </td> 
   <td colname="col3"> <p>Number of days since the first run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Days Since Last Use </p> </td> 
   <td colname="col3"> <p>Number of days since the last use. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Hour of Day </p> </td> 
   <td colname="col3"> <p>Measures the hour in which the app was launched and uses the 24-hour numerical format. </p> <p>This dimension is also used for time parting to determine peak usage times. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Day of Week </p> </td> 
   <td colname="col3"> <p>Number of the week day the app was launched. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Operating System </p> </td> 
   <td colname="col3"> <p>Operating system of the device. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Operating System Version </p> </td> 
   <td colname="col3"> <p>Operating system version. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Days Since Last Upgrade </p> </td> 
   <td colname="col3"> <p>Number of days since the application version number has changed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Launches Since Last Upgrade </p> </td> 
   <td colname="col3"> <p>Number of launches since the application version number has changed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Device Name </p> </td> 
   <td colname="col3"> <p>Stores the device name. </p> <p> <b>iOS</b>: Comma-separated, two-digit string that identifies the iOS device. The first number typically represents the device generation, and the second number typically versions different members of the device family. For a complete list of common device names, see <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/ios/index.html?f=device_versions" format="http" scope="external"> iOS Device Versions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Carrier Name </p> </td> 
   <td colname="col3"> <p>Stores the name of the mobile service provider. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Resolution </p> </td> 
   <td colname="col3"> <p> Width and height in actual pixels. </p> </td> 
  </tr> 
 </tbody> 
</table>

