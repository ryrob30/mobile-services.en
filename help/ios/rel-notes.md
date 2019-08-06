---
description: Release notes and known issues for iOS SDKs 4.x for Experience Cloud Solutions.
seo-description: Release notes and known issues for iOS SDKs 4.x for Experience Cloud Solutions.
seo-title: Release Notes
solution: Marketing Cloud,Analytics
title: Release Notes
topic: Developer and implementation
uuid: e1613dc5-02a4-43a7-997a-29b4de98b4d1
---

# Release notes {#release-notes}

Release notes and known issues for iOS SDKs 4.x for Experience Cloud Solutions.

## Mobile Services releases {#mobile-monthly-releases}

### Release date: July 18, 2019

New features, updates, and fixes to the Android SDKs:

* Adobe Target: All requests now include the client and the `sessionId` in the URL query parameters.
* Adobe Target: Fixed a memory leak.
* Visitor ID Service: The `visitorAppendToURL` and `visitorGetUrlVariablesAsync` APIs no longer double-encode their return values. 

  The double-encoding was causing the return values from those APIs to be flagged by certain security reviews.

For more information about the current and past release notes for all solutions, see [Adobe Experience Cloud Release Notes](https://marketing.adobe.com/resources/help/en_US/whatsnew/).


## Mobile Services hot fixes {#mobile-hot-fixes}

## August 2, 2029

* Reverted a change that was introduced in version 4.18.6 which, in some environments, caused a crash on devices that were running an iOS version older than 11.0.

* Adobe Target: Added the `requestLocationParameters` property in `ADBTargetRequestObject`, which enables the impressionId to be sent with Target requests.
 
### May 24, 2019

**iOS version 4.18.4**

* Visitor ID Service - Increased the return timeout for the 
`visitorGetUrlVariablesAsync` API to 30 seconds.

* Visitor ID Service - The `setPushIdentifier` API call now sends a sync call to the Visitor ID Service every time it is called. 

### June 5, 2019

**iOS version 4.18.5**

* Analytics - Append push opt-in status to Lifecycle data when push notifications are enabled.
