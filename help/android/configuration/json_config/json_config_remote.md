---
description: You can load a different ADBMobile JSON config file when the application starts.
seo-description: You can load a different ADBMobile JSON config file when the application starts.
seo-title: Override the ADBMobile JSON Config Path
solution: Marketing Cloud,Analytics
title: Override the ADBMobile JSON Config Path
topic: Developer and implementation
uuid: 592ed6b4-50f1-4dc6-a69b-90f51ba5a983
index: y
internal: n
snippet: y
translate: y
---

# Override the ADBMobile JSON Config Path

You can load a different ADBMobile JSON config file when the application starts.

The `Config.overrideConfigStream(configInput)` method allows you to specify the path to a different `ADBMobile.json` configuration file when the application starts. This method must be called before any other Experience Cloud SDK call (before `Config.collectLifecycleData()` ), typically in the `onCreate` method of your first loaded activity.

Calling this method with a different path causes a one-time override of the configuration file until the application is closed.

```java
 try { 
 InputStream configInput = getAssets().open("ExampleJSONFile.json"); 
 Config.overrideConfigStream(configInput); 
 } catch (IOException ex) { 
 // do something with the exception if needed 
}
```

