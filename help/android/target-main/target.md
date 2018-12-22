---
description: You can deliver targeted content in Android applications.
keywords: android;library;mobile;sdk
seo-description: You can deliver targeted content in Android applications.
seo-title: Target Configuration
solution: Marketing Cloud,Analytics
title: Target Configuration
topic: Developer and implementation
uuid: 09fe2c9c-7b60-49c3-bb9d-36a30ce7c350
---

# Target Configuration{#target-configuration}

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
