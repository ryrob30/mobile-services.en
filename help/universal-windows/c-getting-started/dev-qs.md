---
description: null
seo-description: null
seo-title: Developer quick start
solution: Marketing Cloud,Analytics
title: Developer quick start
topic: Developer and implementation
uuid: 11c06fcf-d5e4-4858-9a4e-3bf66cdd2a48
---

# Developer quick start{#developer-quick-start}

This guide walks you through the steps to implement the Universal Windows Platform library.

* [Get the SDK](../c-getting-started/dev-qs.md#section_99FE1A17A36D4A2C943939023CF6265C) 
* [Add the Library and Config File to your Project - C#](../c-getting-started/dev-qs.md#section_93C25D893B4A4CD3B996CF3C5590C8DC) 
* [Add the Library and Config File to your Project - C++](../c-getting-started/dev-qs.md#section_A95C1D18F6144F37ADC8F51590F3983E) 
* [Add the Library and Config File to your Project - WinJS](../c-getting-started/dev-qs.md#section_FF83113EBF4742AFA929F4AC28F92DB5) 
* [Update The ADBMobileConfig.json Config File](../c-getting-started/dev-qs.md#section_0BC8CC0E4AAD4AC385FA0AEDC3C56AFE) 
* [Optional - Install and use the Visual Studio Extensions for ADBMobile on Windows Universal App Store apps](../extensions/win-vse-4x.md#concept_F72148BB7B144939BE064F4F2130AEBA)

You'll need Visual Studio 2013 or later to implement the SDK.

## Get the SDK {#section_99FE1A17A36D4A2C943939023CF6265C}

After you unzip the [SDK download](https://github.com/Adobe-Marketing-Cloud/mobile-services/releases), you'll have a separate folder for each supported architecture and platform combination. You will also have an [!DNL ADBMobileConfig.json] file that is explained later in this guide.

## Select the Correct Version {#section_E53C5AA7D5474824A89BB32C003865A1}

Different .dll/.winmd files are provided for each supported architecture (x86, x64, ARM).

>[!NOTE]
>
>The version of `ADBMobile.winmd` does not reflect the version of the library. The `.winmd` file contains metadata only, and as such will have a version number of `255.255.255.255` which is accepted behavior according to Microsoft (see [How do I add assembly information for a WinRT C++ / CX component dll?](https://social.msdn.microsoft.com/Forums/windowsapps/en-US/6bcccaee-aa53-4770-bd5b-1205977f1ca7/how-do-i-add-assembly-information-for-a-winrt-c-cx-component-dll?forum=winappswithnativecode)). In order to check the version of the library you are using, you must check the version of the underlying `ADBMobile.dll` file.

## Syntax Differences {#section_A02DE120B6D240F5AFFE7509755C4F14}

The Universal Windows Platform library can be used in several programming languages. The examples in this guide are in WinJS (JavaScript), and might need to be modified if you are using a different language. Note that when you consume winmd methods from winJS (JavaScript), all methods automatically have their first letter lowercased.

The main difference between the implementations is the data structure used for context data.

Additionally, when using the SDK in a WinJS project, use an empty string ( `""` or `''`) instead of `null` for empty string values.

## Add the Library and Config File to your Project - C# {#section_93C25D893B4A4CD3B996CF3C5590C8DC}

1. Launch Visual Studio and open your solution. 
1. In the **Solution Explorer**, right-click **References** and select **Add Reference**. 

1. [Select the Correct Version](../c-getting-started/dev-qs.md#section_E53C5AA7D5474824A89BB32C003865A1) of the library and then browse to the associated [!DNL ADBMobile.winmd] file. Click **Add**. 

1. Verify that [!DNL ADBMobile.winmd] is checked in the **Reference Manager** window and click **OK**. 

1. In the **Solution Explorer**, right-click **References** and select **Add Reference**. 

1. (Skip this step if you also have a C++ project in your solution) In the **Windows** tab on the left, select **Extensions**, then select and add **Visual C++ 2015 Runtime for Universal Windows Platform Apps**. 

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
1. In the **Solution Explorer**, right-click your project and select **Add** > **References**. 

1. [Select the Correct Version](../c-getting-started/dev-qs.md#section_E53C5AA7D5474824A89BB32C003865A1) of the library and then add a reference to the associated [!DNL ADBMobile.winmd] file. Click **Add**. 

1. Verify that [!DNL ADBMobile.winmd] is checked in the **Reference Manager** window and click **OK**. 

1. Add the following line to your class: 

   ```
   using namespace ADBMobile;
   ```

1. Right-click you your project and select **[!UICONTROL Add]** > **[!UICONTROL Existing Item]**. 

1. Browse to [!DNL ADBMobileConfig.json] and click **[!UICONTROL Add]**. 

1. Right-click [!DNL ADBMobileConfig.json] in your solution and select **[!UICONTROL Properties]**. 

1. On the **[!UICONTROL General]** tab, change **[!UICONTROL Content]** to **[!UICONTROL Yes]** and click **[!UICONTROL OK]**.

## Add the Library and Config File to your Project - WinJS {#section_FF83113EBF4742AFA929F4AC28F92DB5}

1. Launch Visual Studio and open your solution. 
1. In the **Solution Explorer**, right-click **References** and select **Add Reference**. 

1. [Select the Correct Version](../c-getting-started/dev-qs.md#section_E53C5AA7D5474824A89BB32C003865A1) of the library and then browse to the associated [!DNL ADBMobile.winmd] file. Click **Add**. 

1. Verify that [!DNL ADBMobile.winmd] is checked in the **Reference Manager** window and click **OK**. 

1. In the **Solution Explorer**, right-click **References** and select **Add Reference**. 

1. (Skip this step if you also have a C++ project in your solution) In the **Windows** tab on the left, select **Extensions**, then select and add **Visual C++ 2015 Runtime for Universal Windows Platform Apps**. 

1. Right-click you your project and select **[!UICONTROL Add]** > **[!UICONTROL Existing Item]**. 

1. Browse to [!DNL ADBMobileConfig.json] and click **[!UICONTROL Add]**. 

1. Right-click [!DNL ADBMobileConfig.json] in your solution and select **[!UICONTROL Properties]**. 

1. With **[!UICONTROL File Properties]** selected, ensure **[!UICONTROL Package Action]** is set to **[!UICONTROL Content]** (for JavaScript projects, the file is set to Content by default).

## Update The ADBMobileConfig.json Config File {#section_0BC8CC0E4AAD4AC385FA0AEDC3C56AFE}

The `ADBMobileConfig.json` file contains global SDK settings, and is located at your project root after you complete the *Add the Library and Config File to your Project* steps in the previous section. If your [!DNL ADBMobileConfig.json] file was not pre-configured by [Adobe mobile services](https://microsite.omniture.com/t2/help/en_US/mobile/?f=download_sdk), then you need to update a few values to get started.

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

For more details, see [ADBMobileConfig.json Config File Reference](../c-configuration/methods.md#section_5AD4EDF87E304980B4AC4A5657FDA8B9).

## Debugging {#section_3A10376A60394A15BEE483323E0CD4AA}

When you want to enable debugging for the SDK, you have to call `ADBMobile.Config.setDebugLogging(true);`.

For C# and JS apps, you have to enable native code debugging by completing the following steps (native code debugging is the default setting for C++ apps):

**C#**

* Right-click project, select  **[!UICONTROL Properties]** > **[!UICONTROL Debug tab]** . Change the debugger type drop down to **Native Only**.

**JS**

* Right-click project, select  **[!UICONTROL Properties]** > **[!UICONTROL Configuration Properties]** > **[!UICONTROL Debug tab]** . Change the debugger type drop down to **Native Only**.

That's it! You're now ready to implement Analytics, Target, and Audience Management in your Universal Windows Platform app.

Where to go from here:

* [ADBMobile Class and Method Reference](../c-configuration/methods.md#concept_12F12E3E0E434F8CB997AF4027810EBF) 
* [Analytics](../analytics/analytics.md#concept_CAC339E719A74D09B91B457DBF506336) 
* [Target](../target/target.md#concept_CB9A3D33B3404A17AAB44EF5ADE4447D) 
* [Audience Management](../audiencemgmt/audiencemgmt.md#concept_526A892D2DC744B98782004E9583F014)

