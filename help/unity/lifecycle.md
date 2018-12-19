---
description: null
keywords: Unity
seo-description: null
seo-title: Implement Lifecycle
solution: Marketing Cloud,Developer
title: Implement Lifecycle
uuid: 7ff2c194-569c-42a6-922d-dccd2aa9eb8d
index: y
internal: n
snippet: y
---

# Implement Lifecycle{#implement-lifecycle}

See [Lifecycle Metrics](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=metrics) for the metrics and dimensions that can be measured automatically by the mobile library after lifecycle is implemented.

** iOS**

For iOS, lifecycle metrics are automatically collected.

**Android**

In your Unity script, you set the application context for the Android SDK. Add the following code to the `Awake()` function of your FIRST scene:

```
void Awake() 
 { 
  ... 
   
  ADBMobile.SetContext(); 
   
  ... 
 } 

```

To collect lifecycle metrics, add the following code to all of your scene scripts:

```
void OnEnable() 
 { 
  ... 
   
  ADBMobile.CollectLifecycleData (); 
   
  ... 
 } 
 
 void OnDisable() 
 { 
  ... 
   
  ADBMobile.PauseCollectingLifecycleData (); 
   
  ... 
 } 
  
 void OnApplicationPause(bool isPaused) 
 { 
  ... 
   
  if (isPaused) { 
   ADBMobile.PauseCollectingLifecycleData (); 
  }  
  else { 
   ADBMobile.CollectLifecycleData(); 
  } 
   
  ... 
 } 

```

