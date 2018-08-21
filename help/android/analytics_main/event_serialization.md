---
description: Event serialization is not supported by processing rules. In the Mobile SDK, you must use a special syntax in the context data parameter to set serialized events directly on the server call.
keywords: android;library;mobile;sdk
seo-description: Event serialization is not supported by processing rules. In the Mobile SDK, you must use a special syntax in the context data parameter to set serialized events directly on the server call.
seo-title: Event Serialization
solution: Marketing Cloud,Analytics
title: Event Serialization
topic: Developer and implementation
uuid: 23066b43-8ba8-49d6-a35c-b5a3a5fe8585
index: y
internal: n
snippet: y
translate: y
---

# Event Serialization


```
javacdata.put("&amp;&amp;events", "event1:12341234");
```
For example: 

```
java//create a context data dictionary 
HashMap cdata = new HashMap<String, Object>(); 
 
// add events 
cdata.put("&&events", "event1:12341234"); 
 
// send the tracking call - use either a trackAction or TrackState call. 
// trackAction example: 
Analytics.trackAction("action", cdata); 
// trackState example: 
Analytics.trackState("State Name", cdata);
```
