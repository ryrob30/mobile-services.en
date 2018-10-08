---
description: You can deliver targeted content in Android applications.
keywords: android;library;mobile;sdk
seo-description: You can deliver targeted content in Android applications.
seo-title: Target Configuration
solution: Marketing Cloud,Analytics
title: Target Configuration
topic: Developer and implementation
uuid: a7df0ec8-110b-4179-a2d4-a45ff1dbf645
index: y
internal: n
snippet: y
translate: y
---

# Target Configuration

You can deliver targeted content in Android applications.

## Set the Application Context {#section_37CAE496FF894FCA821F7760605574CA}

(Required) The `setContext()` method must be called once in the `onCreate()` method of your main activity.

For example:

```java
@Override 
public void onCreate(Bundle savedInstanceState) { 
  super.onCreate(savedInstanceState); 
  setContentView(R.layout.main); 
  Config.setContext(this.getApplicationContext()); 
}
```

If you already added this method call when you implemented [!DNL Analytics] or [!DNL Audience Management], you do not need to add it again. 
