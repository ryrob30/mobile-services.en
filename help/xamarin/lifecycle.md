---
description: Information to help you implement Lifecycle metrics for Android. Lifecycle metrics are automatically collected for iOS.
keywords: Xamarin
seo-description: Information to help you implement Lifecycle metrics for Android. Lifecycle metrics are automatically collected for iOS.
seo-title: Implement lifecycle
solution: Marketing Cloud,Developer
title: Implement lifecycle
uuid: 6dccc12e-8b57-4231-9c74-d47bc0ac93ba
---

# Implement lifecycle{#implement-lifecycle}

Information to help you implement Lifecycle metrics for Android. Lifecycle metrics are automatically collected for iOS.

See [Lifecycle Metrics](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=metrics) for the metrics and dimensions that can be measured automatically by the mobile library after lifecycle is implemented.

** iOS**

For iOS, lifecycle metrics are automatically collected.

**Android**

In your main activity, you need to set the application context for the Android SDK.

```
protected override void OnCreate (Bundle bundle) 
{ 
    ... 
    Config.SetContext (Application.Context); 
    ... 
}

```

In every activity, you need to implement lifecycle calls.

```
protected override void OnResume() 
{ 
    ... 
    Config.CollectLifecycleData (this); 
    ... 
} 
 
protected override void OnPause() 
{ 
    ... 
    Config.PauseCollectingLifecycleData (); 
    ... 
}
```

