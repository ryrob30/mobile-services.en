---
description: This information helps you get started using Xamarin components for Mobile solutions 4.x SDK.
keywords: Xamarin
seo-description: This information helps you get started using Xamarin components for Mobile solutions 4.x SDK.
seo-title: Xamarin Components for Marketing Cloud Solutions 4.x SDK
solution: Marketing Cloud,Developer
title: Xamarin Components for Marketing Cloud Solutions 4.x SDK
uuid: 1a8aa3c8-f505-4da5-9b40-66f373f926e2
index: y
internal: n
snippet: y
---

# Xamarin Components for Marketing Cloud Solutions 4.x SDK{#xamarin-components-for-marketing-cloud-solutions-x-sdk}

This information helps you get started using Xamarin components for Mobile solutions 4.x SDK.

## Download Xamarin Components {#task_64CDC20730424362809C1A2A6096484A}

<!-- 

get_started.xml

 -->

1. To download the Xamarin components, go to one of the following locations:

    * [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services/releases) 
    * [https://components.xamarin.com/](https://components.xamarin.com/)

## Import the Xamarin Component to your Android Project {#task_A7BAEBFCB84146ADA27178A3B2CF2EEF}

<!-- 

get_started.xml

 -->

To import the ADBMobile component to your Xamarin.Android project: 

1. Open your Xamarin project.
1. Open **[!UICONTROL References]** dialog and then the **[!UICONTROL .Net Assembly]** tab.
1. Select [!DNL ADBMobile.XamarinAndroidBinding.dll] from the folder **[!UICONTROL lib/Android]**.
1. Add your [!DNL ADBMobileConfig.json] file into the **[!UICONTROL Assets]** folder of your project.&nbsp;
1. Add permissions for the following:

    * `INTERNET` 
    * `ACCESS_NETWORK_STATE`

       ```java    
       <uses-permission android:name="android.permission.INTERNET" /> 
       <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
       ```

       If you are using in-app messaging, add the following activity and receiver:     
    
       ```java    
       <activity  
       android:name="com.adobe.mobile.MessageFullScreenActivity"  
       android:theme="@android:style/Theme.Translucent.NoTitleBar" /> 
       <receiver android:name="com.adobe.mobile.MessageNotificationHandler" /> 
       
       ```

       If you are using acquisition, add the following receiver:     
    
       ```java    
       <receiver android:name="com.your.package.name.GPBroadcastReceiver" android:exported="true"> 
           <intent-filter> 
               <action android:name="com.android.vending.INSTALL_REFERRER" /> 
           </intent-filter> 
       </receiver>

       ```

## Import the Xamarin Component to your iOS Project {#task_506FDF2EEAE749FEA780239BA58B0EC0}

<!-- 

get_started.xml

 -->

To import the ADBMobile Component to your Xamarin.iOS project: 

1. Open your Xamarin Project.
1. Open **[!UICONTROL References]** dialog, and then **[!UICONTROL .Net Assembly]** tab.
1. Select [!DNL ADBMobile.XamarinIOSBinding.dll] from the folder **[!UICONTROL lib/ios-unified]**.
1. Add your [!DNL ADBMobileConfig.json] file to the project.

## Get the Components from the Xamarin Components Store {#task_5A62A8903D96414A8B708408D6D2A7D5}

<!-- 

get_started.xml

 -->

To get the components from Xamarin Components Store: 

1. Open your Xamarin Project.
1. Select **[!UICONTROL Component]** and then **[!UICONTROL Get More Components]**.
1. Search **[!UICONTROL Adobe Mobile Services SDK]** add the component to the current project.
1. Add your [!DNL ADBMobileConfig.json] file to the project.&nbsp;

## Making Calls to the Library {#concept_749FD1AAA6DE435D9C9B7760B6EBA86A}

Information to help you make calls to the plugin from your scripts. 

<!-- 

library_calls.xml

 -->

When you want to make calls to the plugin from your scripts, you must import the namespace.

Using [!DNL Com.Adobe.Mobile]:

* **iOS**: Once you have imported the namespace, you can make calls directly to the SDK via the static methods of the `ADBMobile` classes. 

* **Android**: You can make calls directly to the SDK via the static methods of the `Config/Analytics/Target/AudienceManager/Media`classes.

## Implement Lifecycle {#concept_B5C8F76C8E784019B4205206F4CCC5F9}

Information to help you implement Lifecycle metrics for Android. Lifecycle metrics are automatically collected for iOS. 

<!-- 

lifecycle.xml

 -->

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

