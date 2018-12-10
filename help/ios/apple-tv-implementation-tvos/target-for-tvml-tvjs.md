---
description: You can leverage Adobe Target in your TVML/TVJS apps by making direct replacements to your .xml files. Designate areas of your page to be replaced by Target content by using the custom ADBTarget XML element.
seo-description: You can leverage Adobe Target in your TVML/TVJS apps by making direct replacements to your .xml files. Designate areas of your page to be replaced by Target content by using the custom ADBTarget XML element.
seo-title: Adobe Target for TVML/TVJS
title: Adobe Target for TVML/TVJS
uuid: afd5a583-5266-43f2-8cb0-0ace89c53a57
index: y
internal: n
snippet: y
---

# Adobe Target for TVML/TVJS{#adobe-target-for-tvml-tvjs}

You can leverage Adobe Target in your TVML/TVJS apps by making direct replacements to your .xml files. Designate areas of your page to be replaced by Target content by using the custom ADBTarget XML element.

This section contains the following information:

* [Getting Started](../apple-tv-implementation-tvos/target-for-tvml-tvjs.md#section_88445645FD67416EAF6FDC3E3D3F5C33) 
* [Configuring Your Mbox in Target](../apple-tv-implementation-tvos/target-for-tvml-tvjs.md#section_F2DA140C34B0421D976046F825B23123) 
* [Configuring Your ADBTarget Element](../apple-tv-implementation-tvos/target-for-tvml-tvjs.md#section_44A7AEC6FC0648ADAD0BACB57D493AFA) 
* [Examples](../apple-tv-implementation-tvos/target-for-tvml-tvjs.md#section_6D6D6E8C7FE147168FC30D83CBC06985)

<a id="section_BDF5ABF4B0B04F19AEDE3D894451E236"></a>

>[!NOTE] {othertype="Prerequisite"}
>
>Before using the `ADBTarget` element in your TVML pages, you must configure your TVML/TVJS app to use the tvOS SDK. For more information, see [Apple TV Implementation with tvOS](../apple-tv-implementation-tvos/apple-tv-implementation-tvos.md#concept_11073AFBA9124EFF8ACEC763F0A72E8C).

## Getting Started {#section_88445645FD67416EAF6FDC3E3D3F5C33}

1. Identify the [!DNL .xml] file in which you want to use your Target location. 
1. Add an `ADBTarget` element to the file as a child of the `<document>` element. 

1. If [!DNL Target] fails to find your Mbox location, or it times out, the value between your `<ADBTarget>` and `</ADBTarget>` tags is used as default content.

## Configuring Your Mbox in Target {#section_F2DA140C34B0421D976046F825B23123}

The returned content from [!DNL Target] replaces all content between `<ADBTarget>` and `</ADBTarget>`, including both `ADBTarget` tags.

>[!TIP]
>
>You should plan what you want to replace accordingly.

Your use case might be as simple as replacing a string value in a label or as complex as replacing an entire page.

## Configuring Your ADBTarget Element {#section_44A7AEC6FC0648ADAD0BACB57D493AFA}

In the `ADBTarget` element, you must provide the Mbox name in the `mbox` property. You can optionally add custom properties to your request in the `customParameterName="customParameterValue"` format. 

<table id="table_0B415FFFB1C942EA97D93159F7EB20B4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Property Name </th> 
   <th colname="col2" class="entry"> Property Type </th> 
   <th colname="col3" class="entry"> Property Value </th> 
   <th colname="col4" class="entry"> Required? </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="codeph"> mbox </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> Name of your Mbox location </td> 
   <td colname="col4"> Yes </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> id </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> Order ID </td> 
   <td colname="col4"> No </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> total </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> Order Total </td> 
   <td colname="col4"> No </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> purchasedProductIds </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> A comma-separated list of purchased product IDs for this order. <p>For example: </p> 
    <codeblock class="syntax c">
      purchasedProductIds="product1,product2,product3" 
    </codeblock> </td> 
   <td colname="col4"> No </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> mboxParameters </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>A list of key-value pairs for <span class="codeph"> mboxParameters </span>. Each entry in this string is separated by a semicolon ( <span class="codeph"> ; </span>), and key-values are separated by a colon <span class="codeph"> : </span> . </p> <p>For example: </p> 
    <codeblock class="syntax c">
      &amp;nbsp;mboxParameters="mboxparameterKey:mboxParameterValue;mboxParameterKey1:mboxParameterValue1;mboxParameterKey2:mboxParameterValue2" 
    </codeblock> </td> 
   <td colname="col4"> No </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="codeph"> customParameterName </span> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> customParameterValue </td> 
   <td colname="col4"> No </td> 
  </tr> 
 </tbody> 
</table>

## Examples {#section_6D6D6E8C7FE147168FC30D83CBC06985}

**Example 1**

The following example uses an `ADBTarget` element in the [!DNL LandingPage.xml.js] page to replace the contents of an alert:

**Configure Target**

Assume that you have an Mbox location named `landingPage` and the offer content is set to be the following:

```
<title>My cool landing page</title> 
<description>Thanks for coming to my page</description> 

```

**Configure landingPage.xml.js**

* Here is the configuration for landingPage.xml.js: 

  ```
  <alertTemplate> 
      <ADBTarget mbox="landingPage">  
          <title>TargetTestPage</title> 
          <description>Load fail or timeout (defaultContent)</description> 
      </ADBTarget>  
  </alertTemplate> 
  
  ```

* If the request to Target is successful, and your offer content is returned, your page will result with:

  ```
  <alertTemplate> 
      <title>My cool landing page</title> 
      <description>Thanks for coming to my page</description> 
  </alertTemplate>
  ```

* If the Target server cannot be reached or the request times out, your page will result with:

  ```
  <alertTemplate> 
      <title>TargetTestPage</title> 
      <description>Load fail or timeout (defaultContent)</description> 
  </alertTemplate>
  ```

**Example 2**

The following example illustrates how to add custom data to your `ADBTarget` element. This method lets you create conditional experiences and offer content for this Mbox location in Target: 

```
<alertTemplate> 
    <ADBTarget mbox="landingPage" customData="custom data" moreCustomData="more custom data"> 
        <title>TargetTestPage</title> 
        <description>Load fail or timeout (defaultContent)</description> 
    </ADBTarget>  
</alertTemplate>
```

