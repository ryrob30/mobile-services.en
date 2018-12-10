---
description: This information helps you migrate from the 3.x or 2.x version of the Android library to version 4.x.
keywords: android;library;mobile;sdk
seo-description: This information helps you migrate from the 3.x or 2.x version of the Android library to version 4.x.
seo-title: Migrating to the Android 4.x Library
solution: Marketing Cloud,Analytics
title: Migrating to the Android 4.x Library
topic: Developer and implementation
uuid: 906e83bb-2faf-4aa2-ac9b-3fba6b833c7e
index: y
internal: n
snippet: y
---

# Migrating to the Android 4.x Library{#migrating-to-the-android-x-library}

This information helps you migrate from the 3.x or 2.x version of the Android library to version 4.x.

>[!IMPORTANT]
>
>The SDK uses `SharedPreferences` to store data that is needed to calculate unique users, lifecycle metrics, and other data related to core SDK functionality.  If you modify or remove the values in `SharedPreferences` that are expected by the SDK, unexpected behavior might result in the form of data inconsistencies.

In the version 4.x library, the public methods are consolidated into one header. Also, all functionality is now accessible through class level methods, so you do not have to keep track of pointers, instances, or singletons.

The following sections walk you through the migration process:

* [Events, Props, and eVars](../getting-started/migration-v3.md#section_76EA6F5611184C5CAE6E62956D84D7B6) 
* [Remove Unused Properties](../getting-started/migration-v3.md#section_145222EAA20F4CC2977DD883FDDBBFC5) 
* [Update Track Calls and Tracking Variables](../getting-started/migration-v3.md#section_96E7D9B3CDAC444789503B7E7F139AB9) 
* [Custom Visitor ID](../getting-started/migration-v3.md#section_2CF930C13BA64F04959846E578B608F3) 
* [Offline Tracking](../getting-started/migration-v3.md#section_5D4CD8CD1BE041A79A8657E31C0D24C6) 
* [Products Variable](../getting-started/migration-v3.md#section_AFBA36F3718C44D29AF81B9E1056A1B4) 
* [Test the Migration](../getting-started/migration-v3.md#section_8ECE0EDA0C3E422B9C9C15C3C5242AA6)

## Events, Props, and eVars {#section_76EA6F5611184C5CAE6E62956D84D7B6}

In version 4, you can no longer assign variables such as events, eVars, props, heirs, and lists in your app. Instead, the SDK uses context data and processing rules to map your app data to Analytics variables for reporting.

Processing rules provide the following advantages:

* You can change your data mapping without submitting an update to the App Store. 
* You can use meaningful names for data instead of setting variables that are specific to a report suite. 
* There is little impact to sending in extra data.

  These values will not appear in reports until they are mapped using processing rules.

>[!TIP]
>
>Values that you assigned directly to variables should be added to the `data` HashMap.

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

## Moving the Configuration File and Migrating to Version 4 {#section_0B844235E0B04DD4B36976A73DB28FB5}

The following tables list the configuration variables that you need to move to the configuration file.

**Moving the configuration file**

1. Move the value that is set for the variable in the first column to the variable in the second column. 
1. Remove the old configuration variable from your code.

**Migrating from version 3.x**

Move the value from the first column to the variable in the second column. 

<table id="table_3F755933E2904E7C9BBF8D89A08A2685"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuration Variable/Method </th> 
   <th colname="col2" class="entry"> Variable in the ADBMobileConfig.json file </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> setOfflineTrackingEnabled </td> 
   <td colname="col2"> <p>"offlineEnabled" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> setOfflineHitLimit </td> 
   <td colname="col2"> <p> "batchLimit" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> reportSuiteIDs </td> 
   <td colname="col2"> <p>"rsids" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingServer </td> 
   <td colname="col2"> <p>"server" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> charSet </td> 
   <td colname="col2"> <p> "charset" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> currencyCode </td> 
   <td colname="col2"> <p> "currency" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ssl </td> 
   <td colname="col2"> <p> "ssl" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkTrackVars </td> 
   <td colname="col2"> <p>Remove, no longer used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkTrackEvents </td> 
   <td colname="col2"> <p>Remove, no longer used. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Migrating from version 2.x**

Move the value from the first column to the variable in the second column. 

<table id="table_6744953BD9034A898FE7F91FA424CD35"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuration Variable </th> 
   <th colname="col2" class="entry"> Variable in the ADBMobileConfig.json file </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> trackOffline </td> 
   <td colname="col2"> <p>"offlineEnabled" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> offlineLimit </td> 
   <td colname="col2"> <p> "batchLimit" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> account </td> 
   <td colname="col2"> <p>"rsids" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingServer </td> 
   <td colname="col2"> <p>"server", remove the "http://" prefix. The protocol prefix is added automatically based on the "ssl" setting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackingServerSecure </td> 
   <td colname="col2"> <p>Remove. For secure connections, define "server" and then enable "ssl". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> charSet </td> 
   <td colname="col2"> <p> "charset" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> currencyCode </td> 
   <td colname="col2"> <p> "currency" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ssl </td> 
   <td colname="col2"> <p> "ssl" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkTrackVars </td> 
   <td colname="col2"> <p>Remove, no longer used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkTrackEvents </td> 
   <td colname="col2"> <p>Remove, no longer used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> timestamp </td> 
   <td colname="col2"> <p>Remove, no longer configurable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> dc </td> 
   <td colname="col2"> <p>Remove, no longer used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> userAgent </td> 
   <td colname="col2"> <p>Remove, no longer configurable. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> dynamicVariablePrefix </td> 
   <td colname="col2"> <p>Remove, no longer used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> visitorNamespace </td> 
   <td colname="col2"> <p>Remove, no longer used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> usePlugins </td> 
   <td colname="col2"> <p>Remove, no longer used. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>useBestPractices </p> <p>all calls to churn measurement (<span class="codeph"> getChurnInstance</span>) </p> </td> 
   <td colname="col2"> <p>Remove, replaced by <a href="../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Update Track Calls and Tracking Variables {#section_96E7D9B3CDAC444789503B7E7F139AB9}

Instead of using the web-focused `track` and `trackLink` calls, the version 4 SDK uses the following methods:

* `trackState`, which are the views that are available in your app, such as `home dashboard`, `app settings`, `cart`, and so on.

  These states are similar to pages on a website, and `trackState` calls increment page views. 

* `trackAction` actions, such as `logons`, `banner taps`, `feed subscriptions`, and so on that occur in your app and that you want to measure.

The `contextData` parameter for both of these methods is a `HashMap<String, Object>`, which contains the name-value pairs that are sent as context data.

**Events, Props, eVars**

In version 4, you can no longer assign variables such as events, eVars, props, heirs, and lists directly in your app. The SDK now uses context data and processing rules to map your app data to Analytics variables for reporting.

Processing rules provide the following advantages:

* You can change your data mapping without submitting an update to the app store. 
* You can use meaningful names for data instead of setting variables that are specific to a report suite. 
* There is little impact to sending in extra data.

  These values will not appear in reports until they are mapped using processing rules. For more information, see [Processing Rules and Context Data](../getting-started/proc-rules.md#concept_1BCA9101D7CF4815ACEB23725816964B).

Values that you were assigning directly to variables should be added to the `data` HashMap. This means that calls to `setProp`, `setEvar`, and assignments to persistent context data should be removed and the values be added to the `data` parameter.

**AppSection/Server, GeoZip, Transaction ID, Campaign, and other standard variables **

Data that you were setting on the measurement object, including the variables listed above, should be added to the `data` HashMap. The only data that is sent with a `trackState` or `trackAction` call is the payload in the `data` parameter.

**Replace Tracking Calls**

Replace the following methods with a call to `trackState` or `trackAction`:

**Migrating from version 3.x**

* `trackAppState (trackState)` 
* `trackEvents (trackAction)` 
* `track (trackAction)` 
* `trackLinkURL (trackAction)`

**Migrating from version 2.x**

* `track (trackState)` 
* `trackLink (trackAction)`

## Custom Visitor ID {#section_2CF930C13BA64F04959846E578B608F3}

Replace the `visitorID` variable with a call to `setUserIdentifier`.

## Offline Tracking {#section_5D4CD8CD1BE041A79A8657E31C0D24C6}

Offline tracking is enabled in [!DNL ADBMobileConfig.json], and all other offline configuration is done automatically.

Remove calls to the following methods:

**Version 3.x**

* `setOnline` 
* `setOffline`

**Version 2.x**

* `forceOffline` 
* `forceOnline`

## Products Variable {#section_AFBA36F3718C44D29AF81B9E1056A1B4}

For more information about the products variable, see [Products Variable](../analytics-main/products/products.md#concept_A3BB7FB891B743C7B2A9028819FB9EE1).

## Test the Migration {#section_8ECE0EDA0C3E422B9C9C15C3C5242AA6}

After you complete the migration, for more information about inspecting the data that is being sent by the Mobile SDK, see [Using Bloodhound to Test Mobile Applications](../bloodhound.md#concept_20BC9E1C41F24A98BF862CF57DD608DA) .

>[!IMPORTANT]
>
>As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided.

