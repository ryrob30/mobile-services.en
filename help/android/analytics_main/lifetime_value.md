---
description: The lifetime value allows you to measure and target on a lifetime value for each Android user. The value can be used to store lifetime purchases, ad views, video completes, social shares, photo uploads, and so on.
seo-description: The lifetime value allows you to measure and target on a lifetime value for each Android user. The value can be used to store lifetime purchases, ad views, video completes, social shares, photo uploads, and so on.
seo-title: Visitor Lifetime Value
solution: Marketing Cloud,Analytics
title: Visitor Lifetime Value
topic: Developer and implementation
uuid: 59caaa97-8adb-45e6-905e-92b526ad2f43
index: y
internal: n
snippet: y
translate: y
---

# Visitor Lifetime Value

The lifetime value allows you to measure and target on a lifetime value for each Android user. The value can be used to store lifetime purchases, ad views, video completes, social shares, photo uploads, and so on.

Each time you send in a value with `trackLifetimeValueIncrease`, the value is added to the existing value. Lifetime value is stored on device and can be retrieved at any time by calling `lifetimeValue`.

## Track the Visitor Lifetime Value {#section_390943A49AF841F2941E65D6DF2B3F5A}

1. Add the [library to your project and implement lifecycle](../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972). 
1. Import the library: 

   ```java
   import com.adobe.mobile.*;
   ```

1. Call `trackLifetimeValueIncrease` with the amount to increase the value: 

   ```java
   Analytics.trackLifetimeValueIncrease(BigDecimal.valueOf(5.0), null);
   ```

## Send Additional Data {#section_3EBE813E54A24F6FB669B2478B5661F9}

In addition to the lifetime value, you can also send additional context data with each track action call:

```java
HashMap cdata = new HashMap<String, Object>(); 
cdata.put("myapp.ImageLiked", imageName); 
Analytics.trackLifetimeValueIncrease(BigDecimal.valueOf(5.0), cdata);
```

Context data values must be mapped to custom variables in [Adobe Mobile services](https://mobilemarketing.adobe.com):

<a id="fig_3BBB83130B0B4008B5CFBC4C27DAD4D8"></a>

![](assets/map-variable-context-ltv.png) 
