---
description: This information helps you retrieve locally stored, Experience Cloud SDK identities from your iOS app and with GDPR data access requests.
seo-description: This information helps you retrieve locally stored, Experience Cloud SDK identities from your iOS app and with GDPR data access requests.
seo-title: Retrieving Stored Identifiers
title: Retrieving Stored Identifiers
uuid: ba32a388-8b68-4afd-a1ff-b631d0039af6
index: y
internal: n
snippet: y
translate: y
---

# Retrieving Stored Identifiers

This information helps you retrieve locally stored, Experience Cloud SDK identities from your iOS app and with GDPR data access requests.

For more information about GDPR, see [GDPR and Your Business](https://www.adobe.com/privacy/general-data-protection-regulation.html).

>[!IMPORTANT]
>
>The `getAllIdentifiersAsync` method retrieves identities stored in the Experience Cloud SDKs. You must call this method **before** the user opts-out.

Experience Cloud SDK identities (as applicable) are locally stored and returned in a JSON string, which might contain:

* Company Context - IMS Org IDs 
* User IDs 
* Marketing Cloud ID (MCID) 
* Integration Codes (ADID, Push ID) 
* Data Source IDs (DPID, DPUUID) 
* Analytics IDs (AVID, AID, VID, and associated RSIDs) 
* Target Legacy IDs (TNTID, TNT3rdpartyID) 
* Audience Manager ID (UUID)

Here is an example of the `ADBMobile getAllIdentifiersAsync` method in iOS:

```
[ADBMobile getAllIdentifiersAsync:^(NSString * _Nullable content){
      NSLog(content) 
}]
```

