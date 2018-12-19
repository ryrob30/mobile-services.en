---
description: This topic describes how to get started using Xamarin components for Mobile solutions 4.x SDK.
keywords: Xamarin
seo-description: This topic describes how to get started using Xamarin components for Mobile solutions 4.x SDK.
seo-title: Xamarin components for Experience Cloud Solutions 4.x SDK
solution: Marketing Cloud,Developer
title: Xamarin components for Experience Cloud Solutions 4.x SDK
uuid: e7a48107-bd0e-47d6-b49c-dfdae189ac37
index: y
internal: n
snippet: y
---

# Xamarin components for Experience Cloud Solutions 4.x SDK{#xamarin-components-for-experience-cloud-solutions-x-sdk}

This topic describes how to get started using Xamarin components for Mobile solutions 4.x SDK.

Last Updated:**October 20, 2016**

## Getting Started {#section_59D434C30C8F4765A7DEFE877D5268D0}

Download the Xamarin components from [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services/releases) or [https://components.xamarin.com/](https://components.xamarin.com/).

## Android {#section_9CAE1BFD359242568D8288C12A4B7A7D}

Import the ADBMobile Component to your Xamarin.Android Project:

1. Open your Xamarin Project 
1. Open **[!UICONTROL References]** dialog, and then **[!UICONTROL .Net Assembly]** tab. 

1. Select [!DNL ADBMobile.XamarinAndroidBinding.dll] from the folder **[!UICONTROL lib/Android]**. 

1. Add your [!DNL ADBMobileConfig.json] file into the **[!UICONTROL Assets]** folder of your project.&nbsp; 

1. Add permissions for:

    * `INTERNET` 
    * `ACCESS_NETWORK_STATE`

```java
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

Add the following activity and receiver if you are using In-app messaging:

```java
<activity 
android:name="com.adobe.mobile.MessageFullScreenActivity" 
android:theme="@android:style/Theme.Translucent.NoTitleBar" />
<receiver android:name="com.adobe.mobile.MessageNotificationHandler" />

```

Add the following receiver if you are using acquisition:

```java
<receiver android:name="com.your.package.name.GPBroadcastReceiver" android:exported="true">
    <intent-filter>
        <action android:name="com.android.vending.INSTALL_REFERRER" />
    </intent-filter>
</receiver>

```

## iOS {#section_1531928DDE904D769B3987BF927D0E02}

Import the ADBMobile Component to your Xamarin.iOS Project:

1. Open your Xamarin Project. 
1. Open **[!UICONTROL References]** dialog, and then **[!UICONTROL .Net Assembly]** tab. 

1. Select [!DNL ADBMobile.XamarinIOSBinding.dll] from the folder **[!UICONTROL lib/ios-unified]**. 

1. Add your [!DNL ADBMobileConfig.json] file to the project.

## Xamarin Components {#section_82E57DC306094008BCDCE0EFB68F5BCC}

Get the components from Xamarin Components Store:

1. Open your Xamarin Project. 
1. Select **[!UICONTROL Component]** and then **[!UICONTROL Get More Components]**. 

1. Search **[!UICONTROL Adobe Mobile Services SDK]** add the component to the current project. 
1. Add your [!DNL ADBMobileConfig.json] file to the project.&nbsp;


