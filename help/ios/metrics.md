---
description: The following tables list the metrics and dimensions that can be automatically measured by the mobile library after lifecycle is implemented.
seo-description: The following tables list the metrics and dimensions that can be automatically measured by the mobile library after lifecycle is implemented.
seo-title: Lifecycle Metrics
solution: Marketing Cloud,Analytics
title: Lifecycle Metrics
topic: Developer and implementation
uuid: b795e383-d59b-4a3c-9e14-ffe8fb58412c
---

# Lifecycle Metrics {#lifecycle-metrics}

The following tables list the metrics and dimensions that can be automatically measured by the mobile library after lifecycle is implemented.


## Lifecycle Metrics and Dimensions {#section_78F036C4296F4BA3A47C2044F79C86C1}

After lifecycle metrics are configured, the metrics are sent in context data parameters to [!DNL Analytics], parameters to [!DNL Target] with each mbox call, and as a signal to [!DNL Audience Manager]. [!DNL Analytics] and [!DNL Target] use the same format, while [!DNL Audience Manager] uses a different prefix for each metric.

For [!DNL Analytics], the context data that is sent with each lifecycle tracking call is automatically captured in and reported by using the metric or dimension that listed in the first column.

>[!TIP]
>
>Exceptions are provided in the description.

### Metrics

| Metric | Analytics Context Data/Target Parameter | Audience Manager Signal | Description |
|--- |--- |--- |--- |
|First Launches|`a.InstallEvent`|`c_a_InstallEvent`|Triggered at the first run after installation or re-installation.|
|Upgrades|`a.UpgradeEvent`|`c_a_UpgradeEvent`|Triggered at the first run after upgrade or anytime the version number changes.|
|Daily Engaged Users|`a.DailyEngUserEvent`|`c_a_DailyEngUserEvent`|Triggered when the application is used on a particular day.|
|Monthly Engaged Users|`a.MonthlyEngUserEvent`|`c_a_MonthlyEngUserEvent`|Triggered when the application is used during a particular month.|
|Launches|`a.LaunchEvent`|`c_a_LaunchEvent`|Triggered on every run, including crashes and installs. Also triggered when the app is resumed from the background after the lifecycle session timeout is exceeded.|
|Crashes|`a.CrashEvent`|`c_a_CrashEvent`|Triggered when the application is not backgrounded before closing. The event is sent when the application is started again after the crash.  Adobe Mobile crash reporting does not implement a global uncaught exception handler.|
|Previous Session Length|`a.PrevSessionLength`|`c_a_PrevSessionLength`|Reports the number of seconds that a previous application session lasted based on how long the application was open and in the foreground.|

>[!IMPORTANT]
>
>The *Daily Engaged Users* and *Monthly Engaged Users* metrics are not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture these metrics.

### Dimensions

|  Dimension  | Analytics Context Data/Target  | Audience Management  | Description  |
|--- |--- |--- |--- |
|Install Date|a.InstallDate|c_a_InstallDate|Date of first launch after installation.  MM/DD/YYYY|
|App ID|`a.AppID`|`c_a_AppID`|Stores the Application name and version in the `[AppName] [BundleVersion]` format.   For example, `myapp 1.1`.|
|Launch Number|`a.Launches`|`c_a_Launches`|Number of times the application was launched or brought out of the background.|
|Days since first use|`a.DaysSinceFirstUse`|`c_a_DaysSinceFirstUse`|Number of days since first run.|
|Days since last use|a.DaysSinceLastUse|c_a_DaysSinceLastUse|Number of days since last use.|
|Hour of Day|`a.HourOfDay`|`c_a_HourOfDay`|Measures the hour the app was launched and uses the 24-hour numerical format. Used for time parting to determine peak usage times.|
|Day of Week|`a.DayOfWeek`|`c_a_DayOfWeek`|Number of the week day the app was launched.|
|Operating System Version|a.OSVersion|c_a_OSVersion|OS version.|
|Days since last upgrade|`a.DaysSinceLastUpgrade`|`c_a_DaysSinceLastUpgrade`|Number of days since the application version number has changed.|
|Launches since last upgrade|`a.LaunchesSinceUpgrade`|`c_a_LaunchesSinceUpgrade`|Number of launches since the application version number has changed.|
|Device Name|`a.DeviceName`|`c_a_DeviceName`|Stores the device name.  Comma-separated two-digit string that identifies the iOS device. The first number typically represents the device generation, and the second number typically versions different members of the device family. For a list of common device names, see  iOS Device Versions.|
|Carrier Name|`a.CarrierName`|`c_a_CarrierName`|Stores the name of the mobile service provider as provided by the device.|
|Resolution|a.Resolution|c_a_Resolution|Width x Height in actual pixels.|

>[!IMPORTANT]
>
>The *Days since last upgrade*, *Launches since last upgrade*, and the *Carrier Name* dimensions are not automatically stored in an Analytics variable. You must create a processing rule to copy the values to an Analytics variable for reporting.


## Additional Mobile Metrics and Dimensions {#section_0B32BBF9CA734103BEDB5E755FFE5B31}

The following metrics and dimensions are captured in mobile solution variables by the method listed in the **Description** column.

### Metrics

| Event  | Analytics Context Data/Target Parameter  | Audience Management Trait  | Description  |
|--- |--- |--- |--- |
|Action Time Total|`a.action.time.total`|`c_a_action_time_total`|Populated by  trackTimedAction methods.|
|Action Time In App|`a.action.time.inapp`|`c_a_action_time_inapp`|Populated by  trackTimedAction methods.|
|Lifetime Value (event)|`a.ltv.amount`|`c_a_ltv_amount`|Populated by  trackLifetimeValue methods.|

### Dimensions

|  Dimension  | Analytics Context Data/Target Parameter  | Audience Management Trait  | Description  |
|--- |--- |--- |--- |
|Location (down to 10 km)|`a.loc.lat.a`  `a.loc.lon.a`|`c_a_loc_lat_a  `c_a_loc_lon_a|Populated by  trackLocation methods.|
|Location (down to 100 m)|`a.loc.lat.b`  `a.loc.lon.b`|`c_a_loc_lat_b`  `c_a_loc_lon_b`|Populated by  trackLocation methods.|
|Location (down to 1 m)|`a.loc.lat.c`  `a.loc.lon.c`|`c_a_loc_lat_c`  `c_a_loc_lon_c`|Populated by  trackLocation methods.|
|Point of Interest Name|`a.loc.poi`|`c_a_loc_poi`|Populated by  trackLocation methods when device is in a defined POI.|
|Distance to Point of Interest Center|`a.loc.dist`|`c_a_loc_dist`|Populated by  trackLocation methods when device is in a defined POI.|
|Lifetime Value (conversion variable)|`a.ltv.amount`|`c_a_ltv_amount`|Populated by  trackLifetimeValue methods.|
|Tracking Code|`a.referrer.campaign.trackingcode`|`c_a_referrer_campaign_trackingcode`|Populated by Mobile App Acquisition. Generated automatically by Adobe mobile services.|
|Campaign|`a.referrer.campaign.name`|`c_a_referrer_campaign_name`|Name of the campaign, also stored in the  campaign variable. Populated by Mobile App Acquisition.|
|Campaign Content|`a.referrer.campaign.content`|`c_a_referrer_campaign_content`|The name or ID of the content that displayed the link. Populated by Mobile App Acquisition.|
|Campaign Medium|`a.referrer.campaign.medium`|`c_a_referrer_campaign_medium`|Marketing medium, such as banner or email. Populated by Mobile App Acquisition.|
|Campaign Source|`a.referrer.campaign.source`|`c_a_referrer_campaign_source`|Original referrer, such as newsletter or social media network. Populated by Mobile App Acquisition.|
|Campaign Term|`a.referrer.campaign.term`|`c_a_referrer_campaign_term`|Paid keywords or other terms you want to track with this acquisition. Populated by Mobile App Acquisition.|

