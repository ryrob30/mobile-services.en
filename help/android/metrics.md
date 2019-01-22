---
description: Here are the metrics and dimensions that can be measured automatically by the mobile library, after lifecycle is implemented, and a link to troubleshoot Lifecycle data.
keywords: android;library;mobile;sdk
seo-description: Here are the metrics and dimensions that can be measured automatically by the mobile library, after lifecycle is implemented, and a link to troubleshoot Lifecycle data.
seo-title: Lifecycle Metrics
solution: Marketing Cloud,Analytics
title: Lifecycle Metrics
topic: Developer and implementation
uuid: a8f3ebac-be3b-4948-82bb-105d46cfff6d
---

# Lifecycle Metrics{#lifecycle-metrics}

Here are the metrics and dimensions that can be measured automatically by the mobile library, after lifecycle is implemented, and a link to troubleshoot Lifecycle data.

For more information, go to the Knowledge Base at [Troubleshoot Lifecycle data](https://helpx.adobe.com/analytics/kb/troubleshoot-lifecycle-data.html).


## Lifecycle Metrics and Dimensions {#section_78F036C4296F4BA3A47C2044F79C86C1}

When configured, lifecycle metrics are sent in context data parameters to Analytics, in parameters to Target with each mbox call, and as a signal to audience management. Analytics and Target use the same format, while audience management uses a different prefix for each metric.

For Analytics, the context data that is sent with each lifecycle tracking call is automatically captured in and reported on by using the metric or dimension listed in the first column, with the exceptions noted in the **Description** column.

### Metrics

| Metric  | Analytics Context Data/Target Parameter  | Audience Manager Signal  | Description  |
|--- |--- |--- |--- |
|First Launches|a.InstallEvent|c_a_InstallEvent|Triggered at the first run after installation or re-installation.|
|Upgrades|a.UpgradeEvent|c_a_UpgradeEvent|Triggered at the first run after an upgrade or when the version number changes.|
|Daily Engaged Users|a.DailyEngUserEvent|c_a_DailyEngUserEvent|Triggered when the application is used on a particular day.  Important:  This metric is not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture this metric.|
|Monthly Engaged Users|a.MonthlyEngUserEvent|c_a_MonthlyEngUserEvent|Triggered when the application is used during a particular month.  Important:  This metric is not automatically stored in an Analytics metric. You must create a processing rule that sets a custom event to capture this metric.|
|Launches|a.LaunchEvent|c_a_LaunchEvent|Triggered at every run, including crashes and installs. Also triggered on a resume from the background when the lifecycle session timeout has been exceeded.|
|Crashes|a.CrashEvent|c_a_CrashEvent|Triggered when the application is not backgrounded before being closed. The event is sent when the application is started after the crash.  Adobe Mobile crash reporting does not implement a global uncaught exception handler.|
|Previous Session Length|a.PrevSessionLength|c_a_PrevSessionLength|Reports the number of seconds that a previous application session lasted, based on how long the application was open and in the foreground.|

### Dimensions

|  Dimension  | Analytics Context Data/Target  | Audience Management  | Description  |
|--- |--- |--- |--- |
|Install Date|a.InstallDate|c_a_InstallDate|Date of first launch after installation.  The date format is  MM/DD/YYYY.|
|App ID|a.AppID|c_a_AppID|Stores the application name and version in the following format:    [AppName] [BundleVersion]   An example of this format is  myapp 1.1.|
|Launch Number|a.Launches|c_a_Launches|Number of times the application was launched or brought out of the background.|
|Days since first use|a.DaysSinceFirstUse|c_a_DaysSinceFirstUse|Number of days since the first run.|
|Days since last use|a.DaysSinceLastUse|c_a_DaysSinceLastUse|Number of days since the last use.|
|Hour of Day|a.HourOfDay|c_a_HourOfDay|Measures the hour that the app was launched.  This metric uses the 24-hour numerical format and is used for time parting to determine peak usage times.|
|Day of Week|a.DayOfWeek|c_a_DayOfWeek|Number of the day in a week when the app was launched.|
|Operating System Version|a.OSVersion|c_a_OSVersion|OS version.|
|Days since last upgrade|a.DaysSinceLastUpgrade|c_a_DaysSinceLastUpgrade|Number of days since the application version number has changed.  Important:  This metric is not automatically stored in an Analytics variable. You must create a processing rule to copy this value to an Analytics variable for reporting.|
|Launches since last upgrade|a.LaunchesSinceUpgrade|c_a_LaunchesSinceUpgrade|Number of launches since the application version number has changed.  Important:  This metric is not automatically stored in an Analytics variable. You must create a processing rule to copy this value to an Analytics variable for reporting.|
|Device Name|a.DeviceName|c_a_DeviceName|Stores the device name.|
|Carrier Name|a.CarrierName|c_a_CarrierName|Stores the name of the mobile service provider as provided by the device.  Important:  This metric is not automatically stored in an Analytics variable. You must create a processing rule to copy this value to an Analytics variable for reporting.|
|Resolution|a.Resolution|c_a_Resolution|Width x Height in actual pixels.|


## Additional Mobile Metrics and Dimensions {#section_0B32BBF9CA734103BEDB5E755FFE5B31}

The following metrics and dimensions are captured in mobile solution variables by the method listed in the **Description** column.

### Metrics

| Event  | Analytics Context Data/Target Parameter  | Audience Management Trait  | Description  |
|--- |--- |--- |--- |
|Action Time Total|a.action.time.total|c_a_action_time_total|Populated by  trackTimedAction methods.|
|Action Time In App|a.action.time.inapp|c_a_action_time_inapp|Populated by  trackTimedAction methods.|
|Lifetime Value (event)|a.ltv.amount|c_a_ltv_amount|Populated by  trackLifetimeValue methods.|

### Dimensions

|  Dimension  | Analytics Context Data/Target Parameter  | Audience Management Trait  | Description  |
|--- |--- |--- |--- |
|Location (down to 10 km)|a.loc.lat.a  a.loc.lon.a|c_a_loc_lat_a  c_a_loc_lon_a|Populated by  trackLocation methods.|
|Location (down to 100 m)|a.loc.lat.b  a.loc.lon.b|c_a_loc_lat_b  c_a_loc_lon_b|Populated by  trackLocation methods.|
|Location (down to 1 m)|a.loc.lat.c  a.loc.lon.c|c_a_loc_lat_c  c_a_loc_lon_c|Populated by  trackLocation methods.|
|Point of Interest Name|a.loc.poi|c_a_loc_poi|Populated by  trackLocation methods when device is within a defined POI.|
|Distance to Point of Interest Center|a.loc.dist|c_a_loc_dist|Populated by  trackLocation methods when device is within a defined POI.|
|Lifetime Value (conversion variable)|a.ltv.amount|c_a_ltv_amount|Populated by  trackLifetimeValue methods.|
|Tracking Code|a.referrer.campaign.trackingcode|c_a_referrer_campaign_trackingcode|Populated by Mobile App Acquisition and automatically generated by Adobe mobile services.|
|Campaign|a.referrer.campaign.name|c_a_referrer_campaign_name|Name of the campaign, also stored in the  campaign variable. Populated by Mobile App Acquisition.|
|Campaign Content|a.referrer.campaign.content|c_a_referrer_campaign_content|The name or ID of the content that displayed the link. Populated by Mobile App Acquisition.|
|Campaign Medium|a.referrer.campaign.medium|c_a_referrer_campaign_medium|Marketing medium, such as a banner or email. Populated by Mobile App Acquisition.|
|Campaign Source|a.referrer.campaign.source|c_a_referrer_campaign_source|Original referrer, such as a newsletter or a social media network. Populated by Mobile App Acquisition.|
|Campaign Term|a.referrer.campaign.term|c_a_referrer_campaign_term|Paid keywords or other terms that you want to track with this acquisition. Populated by Mobile App Acquisition.|


