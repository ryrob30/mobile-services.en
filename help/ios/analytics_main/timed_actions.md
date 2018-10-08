---
description: Timed actions allow you to measure the in-app time and total time between the start and the end of an action. The SDK calculates the amount of time in each session and the total time across-sessions that it will take for the action to be completed. You can use timed actions to define segments and compare time to purchase, pass level, checkout flow, and so on.
seo-description: Timed actions allow you to measure the in-app time and total time between the start and the end of an action. The SDK calculates the amount of time in each session and the total time across-sessions that it will take for the action to be completed. You can use timed actions to define segments and compare time to purchase, pass level, checkout flow, and so on.
seo-title: Timed Actions
solution: Marketing Cloud,Analytics
title: Timed Actions
topic: Developer and implementation
uuid: 559e093e-ef40-4589-8f1f-63977c389f61
index: y
internal: n
snippet: y
translate: y
---

# Timed Actions

Timed actions allow you to measure the in-app time and total time between the start and the end of an action. The SDK calculates the amount of time in each session and the total time across-sessions that it will take for the action to be completed. You can use timed actions to define segments and compare time to purchase, pass level, checkout flow, and so on.

The following metrics are reported for timed actions:

* Total # of seconds in app between start and end - cross sessions 
* Total # of seconds between start and end (clock time)

An optional callback allows you to take additional action when the timed action completes:

* Run code and add any logic - optional custom logic based on duration results. 
* Add context data prior to passing in durations. 
* Cancel hit and durations not yet sent.

## Tracking Timed Actions {#section_FF5B1EDC1A5340A5B13BC0F1BF2E13E1}

1. Add the [library to your project and implement lifecycle](../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972). 
1. Import the library:

   ```
   #import "ADBMobile.h"
   ```

1. Call `trackTimedActionStart` and provide a timed action name and optional context data.

   ```
   [ADBMobile trackTimedActionStart:@"TimeUntilPurchase"  
                               data:@{@"ExperienceName" : experience}];
   ```

1. (Optional) To add additional context data at any time, you can call `trackTimedActionUpdate` with the timed action name.

   ```
   [ADBMobile trackTimedActionUpdate:@"TimeUntilPurchase"  
                                data:@{@"myapp.ImageLiked" : imageName}];
   ```

1. When the event completes, call `trackTimedActionEnd` and pass the timed action name and `TimedActionBlock` (callback), which will look up all data and calculate durations.

   Timed event metrics are saved in mobile solution variables for automatic reporting. 

   ```
   [ADBMobile trackTimedActionEnd:@"TimeUntilPurchase"  
                            logic:nil];
   ```

## Sending Additional Data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the timed action name, you can send additional context data with the action start and action update calls: 

```
[ADBMobile trackTimedActionUpdate:@"TimeUntilPurchase"  
                             data:@{@"myapp.ImageLiked" : imageName}];
```

Context data values must be mapped to custom variables in [Adobe Mobile services](https://mobilemarketing.adobe.com): 

![](assets/map-variable-context-ltv.png)  

## Examples {#section_7BA344B8BD4F48DCBAE27AC9320CBCEA}

```
// Timed Action Start Example 
[ADBMobile trackTimedActionStart:@"TimeUntilPurchase"  
                            data:@{@"ExperienceName" : experience}];

// Timed Action Update Example 
[ADBMobile trackTimedActionUpdate:@"TimeUntilPurchase"  
                             data:@{@"ImageLiked" : imageName}];

// Timed Action End Example 
[ADBMobile trackTimedActionEnd:@"TimeUntilPurchase"  
                         logic:nil]; 
 
// Timed Action End Example with Callback 
[ADBMobile trackTimedActionEnd:@"TimeUntilPurchase"  
                         logic:^BOOL(NSTimeInterval inAppDuration,  
                                     NSTimeInterval totalDuration,  
                                     NSMutableDictionary *data) { 
                                        [data setObject:@"PurchaseItem" forKey:@"Item453"]; 
                                        return YES; //return YES to send the hit, NO to cancel 
                                     }];
```

