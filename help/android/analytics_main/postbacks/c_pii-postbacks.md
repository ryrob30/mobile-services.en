---
description: You can use the Adobe SDK to collect personally identifiable information (PII) and send it to a third-party endpoint.
seo-description: You can use the Adobe SDK to collect personally identifiable information (PII) and send it to a third-party endpoint.
seo-title: PII Postbacks
title: PII Postbacks
uuid: a152c51e-9790-4672-83ee-c244a95ad0c2
index: y
internal: n
snippet: y
translate: y
---

# PII Postbacks

You can use the Adobe SDK to collect personally identifiable information (PII) and send it to a third-party endpoint.

When you want to use the Adobe SDK to collect PII, you should send a track PII call. Although using this call enables collection of PII data, the SDK does not automatically send the data to an Adobe endpoint. A PII type postback needs to be configured with the appropriate endpoint.

>[!TIP]
>
>An endpoint that supports HTTPS is required to use the PII postback type.

## Tracking PII Postbacks {#section_36B967B888CF467EACCDEF61DFA0B12B}

1. Add [the library to your project and implement lifecycle](https://marketing.adobe.com/resources/help/en_US/mobile/android/dev_qs.html). 
1. Import the library: 

   ```java
   #import "ADBMobile.h"
   ```

1. When you are ready to capture PII, call `trackPII` to send a hit for this action, event, or view: 

   ```java
   [ADBMobile collectPII data:nil];
   ```

