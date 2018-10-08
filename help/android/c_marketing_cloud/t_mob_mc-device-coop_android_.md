---
description: To start using the Experience Cloud Device Co-op, contact your Adobe representative.
seo-description: To start using the Experience Cloud Device Co-op, contact your Adobe representative.
seo-title: Experience Cloud Device Co-op
title: Experience Cloud Device Co-op
uuid: 2b837773-117e-4404-b326-be632f86d41a
index: y
internal: n
snippet: y
translate: y
---

# Experience Cloud Device Co-op

To start using the Experience Cloud Device Co-op, contact your Adobe representative.

To enable your mobile apps for the Experience Cloud Device Co-op, complete the following steps for the Experience Cloud Android SDKs:

>[!IMPORTANT]
>
>This functionality requires Android SDK version 4.8.3 or later.

Starting in SDK version 4.16.1, Device Co-op members can opt their mobile device data out of the Experience Cloud Device Co-op. For more information see [ADBMobile JSON Config](../configuration/json_config/json_config.md#concept_0F700EEE71F94B44A0E4000E6C2DA7FB) and the `visitorAPI.js` method for [isCoopSafe](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-coopsafe.html). 

1. Implement the Adobe Mobile SDK.

   For more information, see [Core Implementation and Lifecycle](../getting_started/dev_qs.md#concept_13176B6E37F547D6935E37125F457972).
1. Enable your Experience Cloud ID.

   For more information, see [Experience Cloud ID Configuration](../c_marketing_cloud/mcvid.md#concept_B623676073854D3DAE724082E22ED91A).
1. Pass authenticated identities such as CRM IDs or hashed emails, by using one of the sync methods.

   For more information, see [Experience Cloud ID Service Methods](../c_marketing_cloud/mc_methods.md#concept_EFA674A8220D44E0AC8B2005EDA2E9C6). 