---
description: You can send signals and retrieve visitor segments from audience management.
keywords: android;library;mobile;sdk
seo-description: You can send signals and retrieve visitor segments from audience management.
seo-title: Audience Manager Configuration
solution: Marketing Cloud,Analytics
title: Audience Manager Configuration
topic: Developer and implementation
uuid: 53a3bd1c-4e05-477f-90f0-e9e3206fda8a
index: y
internal: n
snippet: y
translate: y
---

# Audience Manager Configuration


## Set the Application Context {#section_37CAE496FF894FCA821F7760605574CA}

(Required) The ` setContext()` method must be called once in the ` onCreate()` method of your main activity. 

**Example:** 

```
java@Override 
public void onCreate(Bundle savedInstanceState) { 
  super.onCreate(savedInstanceState); 
  setContentView(R.layout.main); 
  Config.setContext(this.getApplicationContext()); 
}
```
If you already added this method call when you implemented [!DNL  Analytics] or [!DNL  Target], you do not need to add it again. 
