---
description: This section describes how to migrate from the 3.x version of a previous Windows mobile SDK to the Windows 8.1 Universal App Store 4.x SDK for Experience Cloud Solutions.
seo-description: This section describes how to migrate from the 3.x version of a previous Windows mobile SDK to the Windows 8.1 Universal App Store 4.x SDK for Experience Cloud Solutions.
seo-title: Migrate to the 4.x SDKs
solution: Marketing Cloud,Analytics
title: Migrate to the 4.x SDKs
topic: Developer and implementation
uuid: e0fe3b7b-cda5-4a91-834c-2c7e17a501a3
---

# Migrate to the 4.x SDKs {#migrate-to-the-x-sdks}

This section describes how to migrate from the 3.x version of a previous Windows mobile SDK to the Windows 8.1 Universal App Store 4.x SDK for Experience Cloud Solutions.

 With the move to version 4.x, all functionality is now accessible through static methods, so no more keeping track of your own objects.

The following sections walk you through migrating from version 3.x to version 4.x.

## Remove Unused Properties {#section_145222EAA20F4CC2977DD883FDDBBFC5}

You probably noticed a new [!DNL ADBMobileConfig.json] file included with your download. This file contains application-specific, global settings and replaces most of the configuration variables that were used in previous versions. Here is an example of an [!DNL ADBMobileConfig.json] file:

```js
{ 
    "version" : "1.0", 
    "analytics" : { 
        "rsids" : "coolApp", 
        "server" : "my.CoolApp.com", 
        "charset" : "UTF-8", 
        "ssl" : false, 
        "offlineEnabled" : true, 
        "lifecycleTimeout" : 300, 
        "privacyDefault" : "optedin", 
        "poi" : [ 
                    ["san francisco",37.757144,-122.44812,7000], 
                    ["santa cruz",36.972935,-122.01725,600] 
                ] 
    }, 
 "target" : { 
  "clientCode" : "myTargetClientCode", 
  "timeout" : 5 
 }, 
 "audienceManager" : { 
  "server" : "myServer.demdex.com" 
 } 
}
```

The following tables list the configuration variables that you need to move to the configuration file. Move the value set for the variable in the first column to the variable in the second column, and then remove the old configuration variable from your code.

## Migrating from 3.x

| Configuration Variable/Method | Variable in ADBMobileConfig.json |
|--- |--- |
|offlineTrackingEnabled|"offlineEnabled"|
|reportSuiteIDs|"rsids"|
|trackingServer|"server"|
|charSet|"charset"|
|currencyCode|"currency"|
|ssl|"ssl"|
|setOfflineHitLimit|Remove, no longer used.|
|linkTrackVars|Remove, no longer used.|
|linkTrackEvents|Remove, no longer used.|

## Update Track Calls and Tracking Variables {#section_96E7D9B3CDAC444789503B7E7F139AB9}

Instead of using the web-focused `Track` and `TrackLink` calls, the version 4 SDK uses two methods that make a little more sense in the mobile world:

* `TrackState` States are the views that are available in your app, such as "home dashboard", "app settings", "cart", and so on. These states are similar to pages on a website, and `trackState` calls increment page views. 

* `TrackAction` Actions are the things that happen in your app that you want to measure, such as "logons", "banner taps", "feed subscriptions", and other metrics. These calls do not increment page views.

The `contextData` parameter for both of these methods contains name-value pairs that are sent as context data.

## Events, Props, eVars

If you've looked at the [ADBMobile Class and Method Reference](/help/windows-appstore/c-configuration/methods.md), you are probably wondering where to set events, eVars, props, heirs, and lists. In version 4, you can no longer assign those types of variables directly in your app. Instead, the SDK uses context data and processing rules to map your app data to Analytics variables for reporting.

Processing rules provide you several advantages:

* You can change your data mapping without submitting an update to the App Store. 
* You can use meaningful names for data instead of setting variables that are specific to a report suite. 
* There is little impact to sending in extra data. These values won’t appear in reports until they are mapped using processing rules.

For more information, see *Processing Rules* in [Analytics](/help/windows-appstore/analytics/analytics.md).

Any values that you were assigning directly to variables should be added to context data instead. This means that calls to `SetProp`, `SetEvar`, and assignments to persistent context data should all be removed and the values added to context data.

**AppSection/Server, GeoZip, Transaction ID, Campaign, and other standard variables **

Any other data that you were setting on the measurement object, including the variables listed above, should be added to context data instead.

To put it simply, the only data sent in with a `TrackState` or `TrackAction` call is the payload in the `data` parameter.

### Replace Tracking Calls

Throughout your code, replace the following methods with a call to `trackState` or `trackAction`:

### Migrating from 3.x

* TrackAppState (TrackState) 
* TrackEvents (TrackAction) 
* Track (TrackAction) 
* TrackLinkURL (TrackAction)

## Custom Visitor ID {#section_2CF930C13BA64F04959846E578B608F3}

Replace the `visitorID` variable with a call to `setUserIdentifier`.

## Offline Tracking {#section_5D4CD8CD1BE041A79A8657E31C0D24C6}

Offline tracking is enabled in [!DNL ADBMobileConfig.json]. All other offline configuration is done automatically.

Throughout your code, remove calls to the following methods:

### Migrating from 3.x

* SetOnline 
* SetOffline

## Products Variable {#section_AFBA36F3718C44D29AF81B9E1056A1B4}

Since the products variable is not available in processing rules, you can use the following syntax to set `products`:

```js
// create a processing rule to set the corresponding product event. 
// for example, set the Product Views event when context data a.action = "product view" 
var cdata = new Windows.Foundation.Collections.PropertySet(); 
cdata["&&products"] = ";Cool Shoe"; 
ADB.Analytics.trackAction("product view", cdata);
```

![](assets/prod-view.png){width="500px"}

The value of `"&&products"` (in this example, the value is `";Cool Shoe`") should follow the products string syntax for the type of event that you are tracking.

## Test the Migration {#section_8ECE0EDA0C3E422B9C9C15C3C5242AA6}

After you have completed the migration, see [Using Bloodhound to Test Mobile Applications](bloodhound.md#concept_20BC9E1C41F24A98BF862CF57DD608DA) to find out how to inspect the data being sent by the mobile SDK.

>[!IMPORTANT]
>
>As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided.

