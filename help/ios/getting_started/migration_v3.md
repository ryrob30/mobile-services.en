---
description: This information helps you migrate from the versions 3.x or 2.x of the iOS library to version 4.x.
seo-description: This information helps you migrate from the versions 3.x or 2.x of the iOS library to version 4.x.
seo-title: Migrating to the 4.x iOS Library
solution: Marketing Cloud,Analytics
title: Migrating to the 4.x iOS Library
topic: Developer and implementation
uuid: 93df230e-3289-4484-ad98-876c4cea34cf
index: y
internal: n
snippet: y
translate: y
---

# Migrating to the 4.x iOS Library


>[!IMPORTANT]
>
>The SDK uses ` NSUserDefaults` to store data that is needed to calculate unique users, lifecycle metrics, and other data related to core SDK functionality.  If you modify or remove the values in ` NSUserDefaults` that are expected by the SDK, unexpected behavior might result in the form of data inconsistencies. 



In the version 4.x of the iOS SDK library, all of the public methods are consolidated into one header. Also, all functionality is now accessible through class level methods, so you do not have to keep track of pointers, instances, or singletons. 

The following sections walk you through the migration process: 


* [ Events, Props, and eVars ](../getting_started/migration_v3.md#section_76EA6F5611184C5CAE6E62956D84D7B6)
* [ Remove Unused Properties ](../getting_started/migration_v3.md#section_145222EAA20F4CC2977DD883FDDBBFC5)
* [ Update Track Calls and Tracking Variables ](../getting_started/migration_v3.md#section_96E7D9B3CDAC444789503B7E7F139AB9)
* [ Custom Visitor ID ](../getting_started/migration_v3.md#section_2CF930C13BA64F04959846E578B608F3)
* [ Offline Tracking ](../getting_started/migration_v3.md#section_5D4CD8CD1BE041A79A8657E31C0D24C6)
* [ Products Variable ](../getting_started/migration_v3.md#section_AFBA36F3718C44D29AF81B9E1056A1B4)
* [ Test the Migration ](../getting_started/migration_v3.md#section_8ECE0EDA0C3E422B9C9C15C3C5242AA6)


## Events, Props, and eVars {#section_76EA6F5611184C5CAE6E62956D84D7B6}

In version 4, you can no longer assign variables such as events, eVars, props, heirs, and lists directly in your app. Instead, the SDK uses context data and processing rules to map your app data to Analytics variables for reporting. 

Processing rules provide the following advantages: 

* You can change your data mapping without submitting an update to the App Store.
* You can use meaningful names for data instead of setting variables that are specific to a report suite.
* There is little impact to sending in extra data. These values will not appear in reports until they are mapped using processing rules. 


>[!TIP]
>
>Values that you were assigning directly to variables should now be added to the ` data` NSDictionary. 



## Remove Unused Properties {#section_145222EAA20F4CC2977DD883FDDBBFC5}

The new [!DNL  ADBMobileConfig.json] file contains application-specific, global settings, and replaces most of the configuration variables that were used in previous versions. Here is an example of an [!DNL  ADBMobileConfig.json] file: 

```
js{ 
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

**Moving the configuration file** 

To move the configuration file: 


1. Move the value that is set for the variable in the first column to the variable in the second column.
1. Remove the old configuration variable from your code.


**Migrating from version 3.x** 

Move the value from the first column to the variable in the second column. 

<table id="table_3F755933E2904E7C9BBF8D89A08A2685"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuration Variable </th> 
   <th colname="col2" class="entry"> Variable in ADBMobileConfig.json </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> offlineTrackingEnabled </td> 
   <td colname="col2"> <p>"offlineEnabled" </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> offlineHitLimit </td> 
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

**Migrating from version 2.x:** 

Move the value from the first column to the variable in the second column. 

<table id="table_6744953BD9034A898FE7F91FA424CD35"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuration Variable </th> 
   <th colname="col2" class="entry"> Variable in ADBMobileConfig.json </th> 
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
   <td colname="col1"> <p>useBestPractices </p> <p>all calls to churn measurement ( <span class="codeph"> getChurnInstance </span>) </p> </td> 
   <td colname="col2"> <p>Remove, replaced by <a href="../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05" format="dita" scope="local"> Lifecycle Metrics </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>


## Update Track Calls and Tracking Variables {#section_96E7D9B3CDAC444789503B7E7F139AB9}

Instead of using the web-focused ` track` and ` trackLink` calls, the version 4 SDK uses the following methods: 

* ` trackState:data:` states are the views that are available in your app, such as ` home dashboard`, ` app settings`, ` cart`, and so on. These states are similar to pages on a website, and ` trackState` calls increment page views. 

* ` trackAction:data:` actions , such as ` logons`, ` banner taps`, ` feed subscriptions`, and other metrics that occur in your app and that you want to measure.
The ` data` parameter for both of these methods is an ` NSDictionary` that contains name-value pairs that are sent as context data. 

**Events, Props, eVars** 

In version 4, you can no longer assign variables such as events, eVars, props, heirs, and lists directly in your app. The SDK now uses context data and processing rules to map your app data to Analytics variables for reporting. 

Processing rules provide the following advantages: 

* You can change your data mapping without submitting an update to the App Store.
* You can use meaningful names for data instead of setting variables that are specific to a report suite.
* There is little impact to sending in extra data. These values will not appear in reports until they are mapped by using processing rules. For more information, see [ Processing Rules and Context Data ](../getting_started/proc_rules.md#concept_4DAF0756D0DB43BD8C0627E023665FA5). 

Values that you assigned directly to variables should be added to the ` data` ` NSDictionary` instead. This means that calls to ` setProp`, ` setEvar`, and assignments to persistent context data should all be removed and the values be added to the ` data` parameter. 

**AppSection/Server, GeoZip, Transaction ID, Campaign, and other standard variables ** 

Data that you were setting on the measurement object, including the variables listed above, should be added to the ` data` ` NSDictionary` instead. The only data that is sent with a ` trackState` or ` trackAction` call is the payload in the ` data` parameter. 

**Replace Tracking Calls** 

In your code, replace the following methods with a call to ` trackState` or ` trackAction`: 

**Migrating from version 3.x** 

* ` trackAppState (trackState)`
* ` trackEvents (trackAction)`
* ` track (trackAction)`
* ` trackWithContextData (trackAction)`
* ` trackLinkURL (trackAction)`
**Migrating from version 2.x** 

* ` track (trackState)`
* ` trackLink (trackAction)`

## Custom Visitor ID {#section_2CF930C13BA64F04959846E578B608F3}

Replace the ` visitorID` variable with a call to ` setUserIdentifier:`. 

## Offline Tracking {#section_5D4CD8CD1BE041A79A8657E31C0D24C6}

Offline tracking is enabled in [!DNL  ADBMobileConfig.json], and all other offline configuration is done automatically. 

In your code, remove calls to the following methods: 

**3.x** 

* ` setOnline`
* ` setOffline`
**2.x** 

* ` forceOffline`
* ` forceOnline`

## Products Variable {#section_AFBA36F3718C44D29AF81B9E1056A1B4}

Since the products variable is not available in processing rules, you can use the following syntax to set ` products`: 

```
//create a processing rule to set the corresponding product event. 
// for example, set prodView event when context data a.action = "product view" 
[ADBMobile trackAction:@"LikeButtonClicked"  
                  data:@{@"&&products" : @";Cool Shoe"}];
```
![](assets/prod-view.png) 
## Test the Migration {#section_8ECE0EDA0C3E422B9C9C15C3C5242AA6}

After you have completed the migration, see [ Using Bloodhound to Test Mobile Applications ](../bloodhound.md#concept_20BC9E1C41F24A98BF862CF57DD608DA) for more information about inspecting the data being that is sent by the mobile SDK. 


>[!IMPORTANT]
>
>As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided.


