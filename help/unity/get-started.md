---
description: This Plug-in lets you send Adobe Analytics calls from your Unity applications.
keywords: Unity
seo-description: This Plug-in lets you send Adobe Analytics calls from your Unity applications.
seo-title: Unity Plug-in for iOS and Android 4.x SDK
solution: Marketing Cloud,Developer
title: Unity Plug-in for iOS and Android 4.x SDK
uuid: 086c6733-565b-4bdb-8ecd-ecc885f2fc4a
index: y
internal: n
snippet: y
---

# Unity Plug-in for iOS and Android 4.x SDK{#unity-plug-in-for-ios-and-android-x-sdk}

This Plug-in lets you send Adobe Analytics calls from your Unity applications.

## Unity Plug-in for iOS and Android 4.x SDK {#topic_3A913774FCB14998ADCB155C487D3D9B}

This Plug-in lets you send Adobe Analytics calls from your Unity applications. 

<!-- 

get_started.xml

 -->

>[!TIP]
>
>The latest update supports Android/iOS SDK 4.13.1.

## Getting Started {#concept_6893C1DD43B3418A9191015DA63AC178}

Download the `ADBMobile.unitypackage` file from GitHub or from your app's [!DNL Manage App Settings] page in [!DNL Adobe Mobile Services]. 

To download this package, go to https://github.com/Adobe-Marketing-Cloud/mobile-services/releases [https://github.com/Adobe-Marketing-Cloud/mobile-services/releases](https://github.com/Adobe-Marketing-Cloud/mobile-services/releases).

The `ADBMobile.unitypackage` contains the following:

* Assets (root)

    * ADBMobile

        * Demo

            * ADBMobileDemo.cs 
            * BooDemo.boo 
            * BooScene.unity 
            * CSharpScene.unity 
            * JavaScriptDemo.js 
            * JavaScriptScene.unity 
            * SecondScene.unity 
            * SecondSceneScript.cs

    * Plugins

        * ADBMobile.cs 
        * Android

            * adobeMobileLibrary-{version}.jar 
            * AndroidManifest.xml 
            * assets

                * ADBMobileConfig.json

        * iOS

            * ADBMobile.h 
            * ADBMobileConfig.json 
            * ADBMobileWrapper.h 
            * ADBMobileWrapper.mm 
            * AdobeMobileLibrary.a

Optional folders: The Demo folder contains Unity scenes and sample code for each of the supported scripting languages. 

## Import the ADBMobile plug-in to your Unity project {#task_64365B88B78A4E648C79B4555EA33F8A}

<!-- 

get_started.xml

 -->

1. Open your Unity project.
1. Double-click **[!UICONTROL ADBMobile.unitypackage]**.
1. Select the folders that you want to import.

## Build Your Project {#concept_30269C0DF1284030A503916BD537C751}

This information helps you build iOS and Android applications using the Unity plugin. 

<!-- 

project.xml

 -->

** iOS**

When you build for iOS, an Xcode Project is created. By default, the [!DNL ADBMobileWrapper.mm] and [!DNL AdobeMobileLibrary.a] files will be in your new project's Libraries group. Perform the following manual steps required to build you app:

1. Add your [!DNL ADBMobileConfig.json] file to the project.

   Ensure that it is a member of the build any targets necessary. 

1. In the **[!UICONTROL Build Phases]** tab of your project, add a link to the following libraries:

    * SystemConfiguration.framework (this one may be linked already) 
    * libsqlite3.0.dylib

>[!TIP]
>
>To use Local Notification In-App messages from the SDK, enable Notifications by [following these steps](https://docs.unity3d.com/ScriptReference/iOS.NotificationServices.RegisterForNotifications.html) in Unity's documentation.

**Android**

When you build for Android, the [!DNL apk] file already includes the [!DNL ADBMobileConfig.json] file in the correct location. By default, the [!DNL AndroidManifest.xml] file in your [!DNL /Plugins/Android] folder is also used.

If you need to use your own custom manifest file, the following changes should be added.

Add permissions for:

* `INTERNET` 
* `ACCESS_NETWORK_STATE`

```java
<uses-permission android:name="android.permission.INTERNET" /> 
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

Add the following activity and receiver if you are using In-app messaging:

```java
<activity android:name="com.adobe.mobile.MessageFullScreenActivity"  
android:theme="@android:style/Theme.Translucent.NoTitleBar" /> 
<receiver android:name="com.adobe.mobile.MessageNotificationHandler" /> 

```

Add the following receiver if you are using acquisition:

```java
<receiver android:name="com.adobe.mobile.ReferralReceiver" android:exported="true"> 
   <intent-filter> 
      <action android:name="com.android.vending.INSTALL_REFERRER" /> 
   </intent-filter> 
</receiver>

```

## Making Calls to the Library {#concept_BAEE1557527B49CCA2318AEC5B94F3E5}

This information helps you make calls to the library with iOS and Android applications using the Unity plugin. 

<!-- 

library_calls.xml

 -->

When you want to make calls to the plug-in from your scripts, you must import the namespace.

* **C#:** using *`com.adobe.mobile;`* 

* **JavaScript:** import *`com.adobe.mobile;`* 

* **boo:** import *`com.adobe.mobile;`*

After you have imported the namespace, you can make calls directly to the plug-in via the static methods of the ADBMobile class. 

## Implement Lifecycle {#concept_E335869A40EA4EF6B7E2EE8D669532CA}

Information to help you implement Lifecycle metrics in your Unity applications. 

<!-- 

lifecycle.xml

 -->

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

