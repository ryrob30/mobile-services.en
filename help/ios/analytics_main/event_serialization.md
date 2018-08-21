---
description: Event serialization is not supported by processing rules. In the Mobile SDK, you must use a special syntax in the context data parameter to set serialized events directly on the server call.
seo-description: Event serialization is not supported by processing rules. In the Mobile SDK, you must use a special syntax in the context data parameter to set serialized events directly on the server call.
seo-title: Event Serialization
solution: Marketing Cloud,Analytics
title: Event Serialization
topic: Developer and implementation
uuid: 2e05313b-caa2-4fc9-906a-c60d5179b781
index: y
internal: n
snippet: y
translate: y
---

# Event Serialization


```
[contextData setObject:@"eventN:serial number" forKey:@"&amp;&amp;events"];
```
For example: 

```
//create a context data dictionary 
NSMutableDictionary *contextData = [NSMutableDictionary dictionary]; 
 
// add events 
[contextData setObject:@"event1:12341234" forKey:@"&&events"]; 
 
// send the tracking call - use either a trackAction or TrackState call. 
// trackAction example: 
[ADBMobile trackAction:@"action" data:contextData]; 
// trackState example: 
[ADBMobile trackState:@"State Name" data:contextData]; 

```
