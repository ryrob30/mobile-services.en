---
description: Release notes and known issues for Android SDK 4.x for Experience Cloud Solutions.
seo-description: Release notes and known issues for Android SDK 4.x for Experience Cloud Solutions.
seo-title: Release Notes
solution: Marketing Cloud,Analytics
title: Release Notes
topic: Developer and implementation
uuid: 16bb4de8-a216-47a8-928c-0b1e1421adcf
---

# Release notes {#release-notes}

Release notes and known issues for Android SDK 4.x for Experience Cloud Solutions.

## Mobile Services releases {#monthly-mobile-releases}

### Release date: July 18, 2019

New features, updates, and fixes to the Android SDKs:

* Adobe Target: All requests now include the client and the sessionId in the URL query parameters.
* In-app Messaging: Fixed an issue where, when a message was trigged with an empty clickthrough URL, Android apps crashed.
* Visitor ID Service: The `Visitor.appendToURL` and `Visitor.getUrlVariablesAsync` APIs no longer double-encode their return values.

   The double-encoding was causing the return values from those APIs to be flagged by certain security reviews.

For more information about the current and past release notes for all solutions, see [Adobe Experience Cloud Release Notes](https://marketing.adobe.com/resources/help/en_US/whatsnew/). 

## Mobile Services hot fixes {#mobile-hot-fixes}

### May 24, 2019

**Android version 4.17.6**

* visitor ID Service - The 
`setPushIdentifier` API call now sends a
sync call to the Visitor ID Service every time it is called. 

* Visitor ID Service - Increased the connect and read
timeouts from 2 seconds to 5 seconds.
