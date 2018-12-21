---
description: iBeacon tracking allows you to measure and target micro locations using iBeacon and Low Energy Bluetooth.
seo-description: iBeacon tracking allows you to measure and target micro locations using iBeacon and Low Energy Bluetooth.
seo-title: iBeacon tracking
solution: Marketing Cloud,Analytics
title: iBeacon tracking
topic: Developer and implementation
uuid: 390883db-027e-4d12-8a16-86d514579db1
---

# iBeacon tracking{#ibeacon-tracking}

iBeacon tracking allows you to measure and target micro locations using iBeacon and Low Energy Bluetooth.

The following beacon data is sent to Analytics and Target when `trackBeacon` is called:

* `a.beacon.uuid` - ProximityUUID of the beacon 
* `a.beacon.major` - Major number of the beacon, such as store number 
* `a.beacon.minor` - Minor number of the beacon, such as a unique number in a store 
* `a.beacon.prox` - The following values represent how close the user is to the beacon:

    * `0` is unknown 
    * `1` is immediate 
    * `2` is near 
    * `3` is far

This section contains the following information:

* [Tracking iBeacons](../location/ibeacon.md#section_FC3F213545944A468B1E6D5D5C8E2F1F) 
* [Sending Additional Data](../location/ibeacon.md#section_3EBE813E54A24F6FB669B2478B5661F9) 
* [Examples](../location/ibeacon.md#section_9749238BCBC148998CB18E97D7670D19)

## Tracking iBeacons {#section_FC3F213545944A468B1E6D5D5C8E2F1F}

1. Add the [library to your project and implement lifecycle](../getting-started/dev-qs.md#concept_13176B6E37F547D6935E37125F457972). 
1. Import the library: 

   ```
   #import "ADBMobile.h"
   ```

1. When a device is within the proximity of a beacon, call `trackBeacon`: 

   ```
   [ADBMobile trackBeacon:beacon data:nil];
   ```

1. When the user leaves the proximity of the beacon, clear the current beacon: 

   ```
   [ADBMobile trackingClearCurrentBeacon];
   ```

## Sending Additional Data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the timed action name, you can send additional context data with each track action call:

```
[ADBMobile trackBeacon:beacon data:@{@"myapp.ImageLiked" : imageName}];
```

Context data values must be mapped to custom variables in [Adobe Mobile services](https://mobilemarketing.adobe.com): 

![](assets/map-variable-context-ltv.png)

## Examples {#section_9749238BCBC148998CB18E97D7670D19}

```
- (void)locationManager:(CLLocationManager *)manager didRangeBeacons:(NSArray *)beacons inRegion:(CLBeaconRegion *)region { 
    if (beacons.count > 0) { 
        CLBeacon *beacon = beacons[0]; 
        // Adobe - track when in range of a beacon 
        [ADBMobile trackBeacon:beacon data:@{@"sampleContextData" : @"sampleContextDataVal"}]; 
    } 
} 
 
// When the user leaves the proximity of the beacon, clear the current beacon 
[ADBMobile trackingClearCurrentBeacon];
```

