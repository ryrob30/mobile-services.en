---
description: The Bloodhound Tool lets you send server calls to a local computer to test mobile applications.
seo-description: The Bloodhound Tool lets you send server calls to a local computer to test mobile applications.
seo-title: Using Bloodhound to test mobile applications
solution: Marketing Cloud,Analytics
title: Using Bloodhound to test mobile applications
topic: Developer and implementation
uuid: 1b9a29db-7928-438e-8729-8429a34d887e
index: y
internal: n
snippet: y
---

# Using Bloodhound to test mobile applications{#using-bloodhound-to-test-mobile-applications}

The Bloodhound Tool lets you send server calls to a local computer to test mobile applications.

>[!IMPORTANT]
>
>As of April 30, 2017, Adobe Bloodhound has been sunset. Starting on May 1, 2017, no additional enhancements and no additional Engineering or Adobe Expert Care support will be provided.

During application development, Bloodhound lets you view server calls locally, and optionally forward the data to Adobe collection servers.

Bloodhound is available for Mac and Windows.

## Requirements {#section_EFAC8254D4984518A50FE784ED41D175}

* An Intel-based Mac computer running Snow Leopard (10.6) or later, or a Windows PC. 
* Network connectivity to your mobile devices or simulators.

## Installation {#section_18C73E5CB662470F8937CCD79B41FB13}

* **Mac**: Open the dmg you downloaded and drag Bloodhound to the Applications folder. 
* **Windows**: Run the installation file you downloaded.

## Using Bloodhound {#section_0AFA172F3D474E068833A03C0BDFAA5B}

After you start the tool, the server is disabled until you click the **[!UICONTROL Start]** button. Click the **[!UICONTROL Start]** button when you are ready to capture server calls from your application.

Optionally, you can specify a custom port number (must be above 1024) before you start the server. If you do not provide a port number, the server automatically selects an open port.

After the server is running, you need to configure your applications or devices to send data to the tool, as discussed in the next section.

## Configure Devices to Send Hits to Bloodhound {#section_8B57A323C28A4B2189804978017CE5ED}

You can change proxy settings on the device to send http requests to the tool. Requests that are sent to the tool can optionally be forwarded to Adobe Data Collection servers.

If your device does not support a proxy, you can send the hits directly to Bloodhound for testing.

>[!IMPORTANT]
>
>Bloodhound does not support SSL tracking. You must disable SSL in the AppMeasurement library when testing using Bloodhound.

**iOS Devices**

The iOS Device must be on the same network as the computer hosting Bloodhound.

1. Navigate to **[!UICONTROL Settings]** > **[!UICONTROL Wi-Fi]**. 

1. Click the blue arrow to the right of your current Wi-Fi network. 
1. Scroll to the **[!UICONTROL HTTP Proxy settings]**. 
1. Select **[!UICONTROL Auto]**. 
1. Enter the Proxy URL and port (from the Bloodhound UI) into the **[!UICONTROL URL]** field.

**Other Devices**

If the device supports proxy auto config, simply use the Proxy URL (From the Bloodhound UI) as the Proxy Auto Config (PAC) URL. Proxy support varies across Android versions, and there are some proxy configuration tools available for Android to simplify configuration.

**Send Hits Directly**

For devices that do not support proxy (iOS Simulator, older Android versions, etc) it is possible to specify Bloodhound as your tracking server in order to capture the hits it generates. To do this set your tracking server to `"<Bloodhound IP>:<Bloodhound Port>"`.

For example:

```
//iOS 
[measure configureMeasurementWithReportSuiteIDs:@"my_rsid" trackingServer:@"10.10.2.2:5000"]; 
measure.ssl = NO; 

```

```java
//Android 
measure.configureMeasurement("my_rsid", "10.10.2.2:5000"); 
measure.ssl = false;
```

```
//WinRT for Windows 8, Windows Phone 8 
measure.ConfigureMeasurement("my_rsid", "10.10.2.2:5000"); 
measure.ssl = false;
```

## Troubleshooting/Common Issues {#section_EAEEF9F9A20144E2A3C6DC555A850E5E}

* Bloodhound only functions with non-ssl tracking. Any tracking hits sent via SSL are not captured, regardless of the method used above.

