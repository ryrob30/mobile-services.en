---
description: Geo-location helps you measure location data by using latitude and longitude and predefined points of interest in your Android apps.
seo-description: Geo-location helps you measure location data by using latitude and longitude and predefined points of interest in your Android apps.
seo-title: Geo-Location and Points of Interest
solution: Marketing Cloud,Analytics
title: Geo-Location and Points of Interest
topic: Developer and implementation
uuid: 27fecd92-fbb6-4cc6-a6da-7961b136fef0
index: y
internal: n
snippet: y
translate: y
---

# Geo-Location and Points of Interest

Each ` trackLocation` call sends the following information: 

* Latitude, longitude, and location in a point of interest (POI) that is defined in the [ Adobe Mobile Services UI ](https://mobilemarketing.adobe.com). This information is passed to mobile solution variables for automatic reporting. 

* Distance from center and accuracy passed as context data. These variables are not captured automatically. You must map these context data variables by using the instructions in [ Sending Additional Data ](../location/geo_poi.md#section_3EBE813E54A24F6FB669B2478B5661F9). 

This section contains the following information: 


* [ Dynamic POI updates ](../location/geo_poi.md#section_3747B310DD5147E2AAE915E762997712)
* [ How to Track ](../location/geo_poi.md#section_B1616E400A7548F9A672F97FEC75AE27)
* [ Sending Additional Data ](../location/geo_poi.md#section_3EBE813E54A24F6FB669B2478B5661F9)
* [ Location Context Data ](../location/geo_poi.md#section_FFB71E6653F9410A89CC6ACC0C9164A9)
* [ Notes ](../location/geo_poi.md#section_931AC1E0D88147E29FE1B6E3CC1E9550)


## Dynamic POI updates {#section_3747B310DD5147E2AAE915E762997712}

Starting in version 4.2, POIs are defined in the Adobe Mobile UI and dynamically synchronized to the app configuration file. This synchronization requires an ` analytics.poi` setting in the [ ADBMobile JSON Config ](../configuration/json_config/json_config.md#concept_0F700EEE71F94B44A0E4000E6C2DA7FB): 

```
js“analytics.poi”: “https://assets.adobedtm.com/…/yourfile.json”,
```
If this is not configured, you must download an updated version of the ` ADBMobile.json` file and add it to your app. For more information, see [ Download the SDK and Testing Tools ](../getting_started/requirements.md#section_044C17DF82BC4FD8A3E409C456CE9A46). 

## Tracking Geo-Location and POIs {#section_B1616E400A7548F9A672F97FEC75AE27}


1. Add the [ library to your project and implement lifecycle ](../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972).
1. Import the library: 
   ```
   java   import com.adobe.mobile.*;
   ```

1. Call ` trackLocation` to track the current location: 
   ```
   java   Location currentLocation = new Location("my location here"); 
   Analytics.trackLocation(currentLocation, null);
   ```

   >[!TIP]
   >
   >You can call ` trackLocation` at any time. 
   You can use [ Android Location Strategies ](http://developer.android.com/guide/topics/location/strategies.html) to determine the location that is passed to the ` trackLocation` call. 



Additionally, if the location is determined to be in a defined POI radius, an ` a.loc.poi` context data variable is sent in with the ` trackLocation` hit and is reported as a POI on the **[!UICONTROL  Location Breakdown]** reports. An ` a.loc.dist` context variable is also sent with the distance in meters from the defined coordinates. 

## Sending Additional Data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the location data, you can send additional context data with each track location call: 

```
javaHashMap<String, Object> locationContextData = new HashMap<String, Object>(); 
locationContextData.put("myapp.location.LocationSource", "GPS"); 
 
Location currentLocation = new Location("my location here"); 
Analytics.trackLocation(currentLocation, locationContextData);
```
Context data values must be mapped to custom variables in the [ Adobe Mobile Services UI ](https://mobilemarketing.adobe.com): 
![](assets/map-location-context-data.png) 
## Location Context Data {#section_FFB71E6653F9410A89CC6ACC0C9164A9}

The latitude and longitude are sent by using three different context data parameters, with each parameter representing a different level of precision, for a total of six context data parameters. 

For example, the coordinates lat = 40.93231, long = -111.93152 represent a location with 1 m precision. This location is split according to the level of precision across the following variables: 

` a.loc.lat.a`= 040.9 

` a.loc.lat.b` = 32 

` a.loc.lat.c` = 31 

` a.loc.lon.a` = -111.9 

` a.loc.lon.b` = 31 

` a.loc.lon.c` = 52 

Some precision levels might appear as ` 00` depending on the accuracy of the current location. For example, if the location is currently accurate to 100m, ` a.loc.lat.c` and ` a.loc.lon.c` will be populated with ` 00`. 

## Additional Information {#section_931AC1E0D88147E29FE1B6E3CC1E9550}

Remember the following information: 


* A ` trackLocation` request sends in the equivalent of a ` trackAction` call.
* POIs are not passed as part of typical ` trackAction` and ` trackState` calls, so you must use a ` trackLocation` call to track POIs.
* ` trackLocation` should be called as often as necessary to track location and POIs. We recommend calling ` trackLocation` when the app starts and then as needed, depending on the app's requirements. 

* POIs are populated only after they are defined in the app's configuration file. The POIs are not applied to historical ` trackLocation` calls that were previously sent. 

* ` trackLocation` calls support sending additional context data similar to ` trackAction` calls.
* When two POIs have overlapping diameters, the first POI that contains the current location is used. If your POIs overlap, you should list POIs in order of most to least granular to ensure that the most granular POI is reported. 


