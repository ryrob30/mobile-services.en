---
description: Beacon tracking allows you to measure and target micro locations by using iBeacon and Bluetooth Low Energy.
keywords: android;library;mobile;sdk
seo-description: Beacon tracking allows you to measure and target micro locations by using iBeacon and Bluetooth Low Energy.
seo-title: Beacon tracking
solution: Marketing Cloud,Analytics
title: Beacon tracking
topic: Developer and implementation
uuid: d6447b25-71a3-4e27-8301-ff46af4a9f86
index: y
internal: n
snippet: y
translate: y
---

# Beacon tracking

Beacon tracking allows you to measure and target micro locations by using iBeacon and Bluetooth Low Energy.

The following beacon data is sent to Analytics and Target when `trackBeacon` is called:

* `a.beacon.uuid` - ProximityUUID of the beacon 
* `a.beacon.major` - Major number of the beacon (such as store number) 
* `a.beacon.minor` - Minor number of the beacon (such as a unique number within a store) 
* `a.beacon.prox` - Values of 0-3 represent how close the user is to the beacon.

  Here is what these values mean:

    * 0 = unknown 
    * 1 = immediate 
    * 2 = near 
    * 3 = far

This beacon data is captured in mobile solution variables.

## Tracking Beacons {#section_FC3F213545944A468B1E6D5D5C8E2F1F}

1. Add the [library to your project and implement lifecycle](../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972). 
1. Import the library: 

   ```java
   import com.adobe.mobile.*;
   ```

1. Gather beacon location.

   Multiple third-party libraries are available to scan Bluetooth LE beacons, depending on the manufacturer of the beacon. 
1. After the beacon information has been obtained, use the following call to track the location: 

   ```java
   // assumed that the following variables will have been retrieved by the 3rd party beacon library 
   String beaconUUID; 
   String major; 
   String minor; 
   Analytics.BEACON_PROXIMITY proximity;  
   // BEACON_PROXIMITY is an enum available in the SDK. Number 0-3 representing how close the 
   // user is to the beacon. 0 unknown, 1 immediate, 2 near, 3 far.  
   Analytics.trackBeacon(beaconUUID, major, minor, proximity, null);
   ```

1. When the user leaves the beacon's proximity, clear the current beacon: 

   ```java
   Analytics.clearBeacon();
   ```

## Sending Additional Data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the beacon data, you can send additional context data with each `trackBeacon` call:

```java
HashMap cdata = new HashMap<String, Object>(); 
cdata.put("myapp.ImageLiked", imageName); 
Analytics.trackBeacon(beaconUUID, major, minor, proximity, cdata);
```

Context data values must be mapped to custom variables in the [Adobe Mobile services](https://mobilemarketing.adobe.com) UI: 

![](assets/map-variable-context-ltv.png)  