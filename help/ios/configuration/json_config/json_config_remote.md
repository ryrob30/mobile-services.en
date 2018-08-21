---
description: You can load a different ADBMobile JSON Config file when the application starts.
seo-description: You can load a different ADBMobile JSON Config file when the application starts.
seo-title: Override the ADBMobile JSON Config Path
solution: Marketing Cloud,Analytics
title: Override the ADBMobile JSON Config Path
topic: Developer and implementation
uuid: 1211cdbe-caf8-4f46-bb88-d55fe9d7018d
index: y
internal: n
snippet: y
translate: y
---

# Override the ADBMobile JSON Config Path

The ` [ADBMobile overrideConfigPath:filePath]` method allows you to specify the path to a different ` ADBMobile.json` configuration file when the application starts. This method must be called in the ` applicationDidFinishLaunchingWithOptions` method, and the call must occur before any other Experience Cloud SDK call, such as ` collectLifecycleData`. 

Calling this method with a different path causes a one-time override of the configuration file until the application is closed. 

For example: 

```
NSString *filePath = [[NSBundle mainBundle] pathForResource:@"ExampleJSONFile" ofType:@"json"]; 
[ADBMobile overrideConfigPath:filePath];
```
