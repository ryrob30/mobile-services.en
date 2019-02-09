---
description: This information helps you migrate from the versions 3.x or 2.x of the iOS library to version 4.x.
seo-description: This information helps you migrate from the versions 3.x or 2.x of the iOS library to version 4.x.
seo-title: Migrating to the 4.x iOS Library
solution: Marketing Cloud,Analytics
title: Migrating to the 4.x iOS Library
topic: Developer and implementation
uuid: 5668972b-f355-4e03-9df0-8c82ddf6809b
---

# Migrating to the 4.x iOS Library{#migrating-to-the-x-ios-library}

This information helps you migrate from the versions 3.x or 2.x of the iOS library to version 4.x.

>[!IMPORTANT]
>
>The SDK uses `NSUserDefaults` to store data that is needed to calculate unique users, lifecycle metrics, and other data related to core SDK functionality.  If you modify or remove the values in `NSUserDefaults` that are expected by the SDK, unexpected behavior might result in the form of data inconsistencies.

In the version 4.x of the iOS SDK library, all of the public methods are consolidated into one header. Also, all functionality is now accessible through class level methods, so you do not have to keep track of pointers, instances, or singletons.

## Events, Props, and eVars {#section_76EA6F5611184C5CAE6E62956D84D7B6}

In version 4, you can no longer assign variables such as events, eVars, props, heirs, and lists directly in your app. Instead, the SDK uses context data and processing rules to map your app data to Analytics variables for reporting.

Processing rules provide the following advantages:

* You can change your data mapping without submitting an update to the App Store. 
* You can use meaningful names for data instead of setting variables that are specific to a report suite. 
* There is little impact to sending in extra data.

  These values will not appear in reports until they are mapped using processing rules.

>[!TIP]
>
>Values that you were assigning directly to variables should now be added to the `data` NSDictionary.

## Remove Unused Properties {#section_145222EAA20F4CC2977DD883FDDBBFC5}

The new [!DNL ADBMobileConfig.json] file contains application-specific, global settings, and replaces most of the configuration variables that were used in previous versions. Here is an example of an [!DNL ADBMobileConfig.json] file:

```js
{ 
    "version" : "1.0", 
    "analytics" : { 
        "rsids" : "coolApp", 
        "server" : "my.CoolApp.com", 
        "charset" : "UTF-8", 
        "ssl" : false, 
        "offlineEnabled" : true, 
        "lifecycleTimeout" : 5, 
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

The following tables list the configuration variables that you need to move to the configuration file.

### Moving the configuration file

To move the configuration file:

1. Move the value that is set for the variable in the first column to the variable in the second column. 
1. Remove the old configuration variable from your code.

### Migrating from version 3.x

Move the value from the first column to the variable in the second column. 

| Configuration Variable | Variable in ADBMobileConfig.json |
|--- |--- |
|offlineTrackingEnabled|"offlineEnabled"|
|offlineHitLimit|"batchLimit"|
|reportSuiteIDs|"rsids"|
|trackingServer|"server"|
|charSet|"charset"|
|currencyCode|"currency"|
|ssl|"ssl"|
|linkTrackVars|Remove, no longer used.|
|linkTrackEvents|Remove, no longer used.|


### Migrating from version 2.x

Move the value from the first column to the variable in the second column. 

| Configuration Variable | Variable in ADBMobileConfig.json |
|--- |--- |
|trackOffline|"offlineEnabled"|
|offlineLimit|"batchLimit"|
|account|"rsids"|
|trackingServer|"server", remove the "https://" prefix. The protocol prefix is added automatically based on the "ssl" setting.|
|trackingServerSecure|Remove. For secure connections, define "server" and then enable "ssl".|
|charSet|"charset"|
|currencyCode|"currency"|
|ssl|"ssl"|
|linkTrackVars|Remove, no longer used.|
|linkTrackEvents|Remove, no longer used.|
|timestamp|Remove, no longer configurable.|
|dc|Remove, no longer used.|
|userAgent|Remove, no longer configurable.|
|dynamicVariablePrefix|Remove, no longer used.|
|visitorNamespace|Remove, no longer used.|
|usePlugins|Remove, no longer used.|
|useBestPractices  all calls to churn measurement (  getChurnInstance )|Remove, replaced by  Lifecycle Metrics .|


## Update Track Calls and Tracking Variables {#section_96E7D9B3CDAC444789503B7E7F139AB9}

Instead of using the web-focused `track` and `trackLink` calls, the version 4 SDK uses the following methods:

* `trackState:data:` states are the views that are available in your app, such as `home dashboard`, `app settings`, `cart`, and so on.

  These states are similar to pages on a website, and `trackState` calls increment page views. 

* `trackAction:data:` actions , such as `logons`, `banner taps`, `feed subscriptions`, and other metrics that occur in your app and that you want to measure.

The `data` parameter for both of these methods is an `NSDictionary` that contains name-value pairs that are sent as context data.

### Events, Props, eVars

In version 4, you can no longer assign variables such as events, eVars, props, heirs, and lists directly in your app. The SDK now uses context data and processing rules to map your app data to Analytics variables for reporting.

Processing rules provide the following advantages:

* You can change your data mapping without submitting an update to the App Store. 
* You can use meaningful names for data instead of setting variables that are specific to a report suite. 
* There is little impact to sending in extra data.

  These values will not appear in reports until they are mapped by using processing rules. For more information, see [Processing Rules and Context Data](/help/ios/getting-started/proc-rules.md).

Values that you assigned directly to variables should be added to the `data` `NSDictionary` instead. This means that calls to `setProp`, `setEvar`, and assignments to persistent context data should all be removed and the values be added to the `data` parameter.

### AppSection/Server, GeoZip, Transaction ID, Campaign, and other standard variables

Data that you were setting on the measurement object, including the variables listed above, should be added to the `data` `NSDictionary` instead. The only data that is sent with a `trackState` or `trackAction` call is the payload in the `data` parameter.

### Replace Tracking Calls

In your code, replace the following methods with a call to `trackState` or `trackAction`:

### Migrating from version 3.x

* `trackAppState (trackState)` 
* `trackEvents (trackAction)` 
* `track (trackAction)` 
* `trackWithContextData (trackAction)` 
* `trackLinkURL (trackAction)`

### Migrating from version 2.x

* `track (trackState)` 
* `trackLink (trackAction)`

## Custom Visitor ID {#section_2CF930C13BA64F04959846E578B608F3}

Replace the `visitorID` variable with a call to `setUserIdentifier:`.

## Offline Tracking {#section_5D4CD8CD1BE041A79A8657E31C0D24C6}

Offline tracking is enabled in [!DNL ADBMobileConfig.json], and all other offline configuration is done automatically.

In your code, remove calls to the following methods:

### Version 3.x

* `setOnline` 
* `setOffline`

### Version 2.x

* `forceOffline` 
* `forceOnline`

## Products Variable {#section_AFBA36F3718C44D29AF81B9E1056A1B4}

Since the products variable is not available in processing rules, you can use the following syntax to set `products`:

```objective-c
//create a processing rule to set the corresponding product event. 
// for example, set prodView event when context data a.action = "product view" 
[ADBMobile trackAction:@"LikeButtonClicked"  
                  data:@{@"&&products" : @";Cool Shoe"}];
```

![](assets/prod-view.png){width="500px"}

## Test the Migration {#section_8ECE0EDA0C3E422B9C9C15C3C5242AA6}

After you have completed the migration, see [Using Bloodhound to Test Mobile Applications](../bloodhound.md#concept_20BC9E1C41F24A98BF862CF57DD608DA) for more information about inspecting the data being that is sent by the mobile SDK.

>[!IMPORTANT]
>
>As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided.

