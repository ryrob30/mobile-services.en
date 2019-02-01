---
description: null
seo-description: null
seo-title: Developer quick start
solution: Marketing Cloud,Analytics
title: Developer quick start
topic: Developer and implementation
uuid: b368959b-d985-436e-8b3e-97e355a97951
---

# Developer quick start{#developer-quick-start}

You'll need Visual Studio 2013 or later to implement the SDK.

## Get the SDK {#section_99FE1A17A36D4A2C943939023CF6265C}

After you unzip the [SDK download](https://github.com/Adobe-Marketing-Cloud/mobile-services/releases), you'll have a separate folder for each supported architecture and platform combination. You will also have an [!DNL ADBMobileConfig.json] file that is explained later in this guide.

## Select the Correct Version {#section_E53C5AA7D5474824A89BB32C003865A1}

Different `.dll`/ `.winmd` files are provided for each target platform (Windows 8.1, Windows Phone 8.1), and supported architecture (x86, x64, ARM). The files are separated into a folder structure according to the following: 

![](assets/folder-structure.png)

>[!IMPORTANT]
>
>The version of `ADBMobile.winmd` does not reflect the version of the library. The `.winmd` file contains metadata only, and as such will have a version number of `255.255.255.255` which is accepted behavior according to Microsoft (see [How do I add assembly information for a WinRT C++ / CX component dll?](https://social.msdn.microsoft.com/Forums/windowsapps/en-US/6bcccaee-aa53-4770-bd5b-1205977f1ca7/how-do-i-add-assembly-information-for-a-winrt-c-cx-component-dll?forum=winappswithnativecode)). To check the version of the library you are using, check the version of the underlying `ADBMobile.dll` file.

## Syntax Differences {#section_A02DE120B6D240F5AFFE7509755C4F14}

The Windows 8.1 Universal App Store library can be used in several programming languages. The examples in this guide are in WinJS (JavaScript), and might need to be modified if you are using a different language. Note that when you consume winmd methods from winJS (JavaScript), all methods automatically have their first letter lowercased.

The main difference between the implementations is the data structure used for context data.

Additionally, when using the SDK in a WinJS project, use an empty string ( `""` or `''`) instead of `null` for empty string values.

## Add the Library and Config File to your Project - C# {#section_93C25D893B4A4CD3B996CF3C5590C8DC}

1. Launch Visual Studio and open your solution. 
1. In the **Solution Explorer**, right-click **[!UICONTROL References]** and select **[!UIUCONTROL Add Reference]**. 

1. [Select the Correct Version](../c-getting-started/dev-qs.md#section_E53C5AA7D5474824A89BB32C003865A1) of the library and then browse to the associated [!DNL ADBMobile.winmd] file. Click **[!UICONTROL Add]**. 

1. Verify that [!DNL ADBMobile.winmd] is checked in the **[!UICONTROL Reference Manager]** window and click **[!UICONTROL OK]**. 

   >[!NOTE]
   >
   >When adding a reference to a Windows Phone app, you will have to change the default file filter from **[!UICONTROL Component Files]** to **All Files** in order to select [!DNL ADBMobile.winmd].

1. In the **[!UICONTROL Solution Explorer]**, right-click **[!UICONTROL References]** and select **[!UICONTROL Add Reference]**. 

1. (Skip this step if you also have a C++ project in your solution) In the **Windows** tab on the left, select **[!UICONTROL Extensions]**, then select and add **[!UICONTROL Microsoft Visual C++ 2013 Runtime Package for Windows]**. 

1. Add the following line to your class: 

   ```
   using ADBMobile;
   ```

1. Right-click you your project and select **[!UICONTROL Add]** > **[!UICONTROL Existing Item]**. 

1. Browse to [!DNL ADBMobileConfig.json] and click **[!UICONTROL Add]**. 

1. Right-click [!DNL ADBMobileConfig.json] in your solution and select **[!UICONTROL Properties]**. 

1. Change **[!UICONTROL Build Action]** to **[!UICONTROL Content]**.

## Add the Library and Config File to your Project - C++ {#section_A95C1D18F6144F37ADC8F51590F3983E}

1. Launch Visual Studio and open your solution. 
1. In the **[!UICONTROL Solution Explorer]**, right-click your project and select **[!UICONTROL Add]** > **[!UICONTROL References]**. 

1. [Select the Correct Version](../c-getting-started/dev-qs.md#section_E53C5AA7D5474824A89BB32C003865A1) of the library and then add a reference to the associated [!DNL ADBMobile.winmd] file. Click **[!UICONTROL Add]**. 

1. Verify that [!DNL ADBMobile.winmd] is checked in the **[!UICONTROL Reference Manager]** window and click **[!UICONTROL OK]**. 

   >[!NOTE]
   >
   >When adding a reference to a Windows Phone app, you will have to change the default file filter from **[!UICONTROL Component Files]** to **All Files** in order to select [!DNL ADBMobile.winmd].

1. Add the following line to your class: 

   ```
   using namespace ADMS::Measurement;
   ```

1. Right-click you your project and select **[!UICONTROL Add]** > **[!UICONTROL Existing Item]**. 

1. Browse to [!DNL ADBMobileConfig.json] and click **[!UICONTROL Add]**. 

1. Right-click [!DNL ADBMobileConfig.json] in your solution and select **[!UICONTROL Properties]**. 

1. On the **[!UICONTROL General]** tab, change **[!UICONTROL Content]** to **[!UICONTROL Yes]** and click **[!UICONTROL OK]**.

## Add the Library and Config File to your Project - WinJS {#section_FF83113EBF4742AFA929F4AC28F92DB5}

1. Launch Visual Studio and open your solution. 
1. In the **Solution Explorer**, right-click **[!UICONTROL References]** and select **[!UICONTROL Add Reference**. 

1. [Select the Correct Version](../c-getting-started/dev-qs.md#section_E53C5AA7D5474824A89BB32C003865A1) of the library and then browse to the associated [!DNL ADBMobile.winmd] file. Click **[!UICONTROL Add]**. 

1. Verify that [!DNL ADBMobile.winmd] is checked in the **[UICONTROL Reference Manager]** window and click **[UICONTROL OK]**. 

   >[!NOTE]
   >
   >When adding a reference to a Windows Phone app, you will have to change the default file filter from **[!UICONTROL Component Files]** to **All Files** in order to select [!DNL ADBMobile.winmd].

1. In the **[!UICONTROL Solution Explorer]**, right-click **[!UICONTROL References]** and select **[!UICONTROL Add Reference]**. 

1. (Skip this step if you also have a C++ project in your solution) In the **Windows** tab on the left, select **Extensions**, then select and add **Microsoft Visual C++ 2013 Runtime Package for Windows**. 

1. Right-click you your project and select **[!UICONTROL Add]** > **[!UICONTROL Existing Item]**. 

1. Browse to [!DNL ADBMobileConfig.json] and click **[!UICONTROL Add]**. 

1. Right-click [!DNL ADBMobileConfig.json] in your solution and select **[!UICONTROL Properties]**. 

1. With **[!UICONTROL File Properties]** selected, ensure **[!UICONTROL Package Action]** is set to **[!UICONTROL Content]** (for JavaScript projects, the file is set to Content by default).

## Update The ADBMobileConfig.json Config File {#section_0BC8CC0E4AAD4AC385FA0AEDC3C56AFE}

The `ADBMobileConfig.json` file contains global SDK settings, and is located at your project root after you complete the steps in the *Add the Library and Config File to your Project* section. If your [!DNL ADBMobileConfig.json] file was not pre-configured by Adobe Mobile Services, you need to update a few values to get started.

The following is an example of an `ADBMobileConfig.json` file:

```js
{ 
    "version" : "1.0", 
    "analytics" : { 
        "rsids" : "coolApp", 
        "server" : "my.CoolApp.com", 
        "charset" : "UTF-8", 
        "ssl" : false, 
        "offlineEnabled" : true, 
        "lifecycleTimeout" : 300, 
        "privacyDefault" : "optedin", 
        "poi" : [ 
                    ["san francisco",37.757144,-122.44812,7000], 
                    ["santa cruz",36.972935,-122.01725,600] 
                ] 
    }, 
 "target" : { 
  "clientCode" : "myTargetClientCode", 
  "timeout" : 1 
 }, 
 "audienceManager" : { 
  "server" : "myServer.demdex.com" 
 } 
}
```

At a minimum, update the following values for the Solutions you are using:

* **Analytics**: `rsids` and `server` 
* **Target**: `clientCode` 
* **Audience Management**: `server`

For more details, see [ADBMobileConfig.json Config File Reference](/help/windows-appstore/c-configuration/methods.md).

## Debugging {#section_3A10376A60394A15BEE483323E0CD4AA}

When you want to enable debugging for the SDK, you have to call `ADBMobile.Config.setDebugLogging(true);`.

For C# and JS apps, you have to enable native code debugging by completing the following steps (native code debugging is the default setting for C++ apps):

### C#

Right-click the project, select  **[!UICONTROL Properties]** > **[!UICONTROL Debug tab]** . Change the debugger type drop down to **Native Only**.

### JS

Right-click the project, select  **[!UICONTROL Properties]** > **[!UICONTROL Configuration Properties]** > **[!UICONTROL Debug tab]** . Change the debugger type drop down to **Native Only**.

That's it! You're now ready to implement Analytics, Target, and Audience Management in your Windows 8.1 Universal App Store app. 
