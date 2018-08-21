---
description: This information helps you retrieve locally stored, SDK identities from your Android app and with GDPR data access requests.
seo-description: This information helps you retrieve locally stored, SDK identities from your Android app and with GDPR data access requests.
seo-title: Retrieving Stored Identifiers
title: Retrieving Stored Identifiers
uuid: f68cbf44-3414-48f8-8b6b-2277939418fb
index: y
internal: n
snippet: y
translate: y
---

# Retrieving Stored Identifiers


>[!IMPORTANT]
>
>The ` getAllIdentifiersAsync` method retrieves identities stored in the SDK. You must call this method **before** the user opts-out. 



SDK identities (as applicable) are locally stored and returned in a JSON string, which might contain: 


* Company Context - IMS Org IDs
* User IDs
* Marketing Cloud ID (MCID)
* Integration Codes (ADID, Push ID)
* Data Source IDs (DPID, DPUUID)
* Analytics IDs (AVID, AID, VID, and associated RSIDs)
* Target Legacy IDs (TNTID, TNT3rdpartyID)
* Audience Manager ID (UUID)


Here is an example of the ` ADBMobile getAllIdentifiersAsync` method in Android: 


```
javaConfig.getAllIdentifiersAsync(new ConfigCallback<String>() { 
     @Override 
     public void call(String identitiesJson) {                 
         Log.d("ADBMobile Identities", identitiesJson); 
     } 
});
```

