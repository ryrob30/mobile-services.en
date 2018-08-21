---
description: Lifetime value lets you measure and target on a lifetime value for each user.
seo-description: Lifetime value lets you measure and target on a lifetime value for each user.
seo-title: Visitor Lifetime Value
solution: Marketing Cloud,Analytics
title: Visitor Lifetime Value
topic: Developer and implementation
uuid: f72f73ce-4af2-4bde-907b-c84b35d90adc
index: y
internal: n
snippet: y
translate: y
---

# Visitor Lifetime Value

Each time you send in a value with ` trackLifetimeValueIncrease`, the value is added to the existing value. Lifetime value is stored on device and can be retrieved at any time by calling ` lifetimeValue`. This can be used to store lifetime purchases, ad views, video completes, social shares, photo uploads, and so on. 

## How to Track {#section_390943A49AF841F2941E65D6DF2B3F5A}


1. Add the [ library to your project and implement lifecycle ](../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972).
1. Import the library: 
   ```
   java   import com.adobe.mobile.*;
   ```

1. Call ` trackLifetimeValueIncrease` with the amount to increase the value: 
   ```
   [ADBMobile trackLifetimeValueIncrease:increaseAmount data:nil];
   ```



## Sending Additional Data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the lifetime value, you can send additional context data with each track action call: 

```
NSMutableDictionary *contextData = [NSMutableDictionary dictionary]; 
[contextData setObject:imageName forKey:@"myapp.ImageLiked"]; 
[ADBMobile trackLifetimeValueIncrease:increaseAmount data:contextData];
```
Context data values must be mapped to custom variables in [ Adobe Mobile services ](https://mobilemarketing.adobe.com): 
![](assets/map-variable-context-ltv.png) 