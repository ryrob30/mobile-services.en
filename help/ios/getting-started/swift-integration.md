---
description: The iOS Adobe Mobile SDK can be seamlessly integrated in a Swift project by using the Mix and Match feature in the iOS Developer Library.
seo-description: The iOS Adobe Mobile SDK can be seamlessly integrated in a Swift project by using the Mix and Match feature in the iOS Developer Library.
seo-title: Swift Integration
solution: Marketing Cloud,Analytics
title: Swift Integration
topic: Developer and implementation
uuid: 5fb77b57-cbf9-4bcf-8b41-65a933bf9336
index: y
internal: n
snippet: y
---

# Swift Integration{#swift-integration}

The iOS Adobe Mobile SDK can be seamlessly integrated in a Swift project by using the Mix and Match feature in the iOS Developer Library.

For more information, see [Swift and Objective-C in the Same Project](https://developer.apple.com/library/ios/documentation/Swift/Conceptual/BuildingCocoaApps/MixandMatch.html).

For example, by using the bridging header method as described in the documentation, you can import the Adobe Mobile iOS SDK header file:

```
#import “ADBMobile.h”
```

To access methods from the SDK in your Swift files, use the following format:

```
ADBMobile.{methodname}
```

