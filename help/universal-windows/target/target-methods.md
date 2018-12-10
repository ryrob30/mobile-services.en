---
description: List of Target methods provided by the Universal Windows Platform library.
seo-description: List of Target methods provided by the Universal Windows Platform library.
seo-title: Target methods
solution: Marketing Cloud,Analytics
title: Target methods
topic: Developer and implementation
uuid: 2ad5953b-7850-446a-8053-b3715b86329b
index: y
internal: n
snippet: y
---

# Target methods{#target-methods}

List of Target methods provided by the Universal Windows Platform library.

The SDK currently has support for multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], and [!DNL Audience Manager].

[Lifecycle Metrics](../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05) are sent as parameters to each mbox load.

>[!NOTE]
>
>When you consume winmd methods from winJS (JavaScript), all methods automatically have their first letter lowercased.

**Class Reference : TargetLocationRequest**

**Properties:**

```
property Platform::String ^name; 
property Platform::String ^defaultContent; 
property Windows::Foundation::Collections::IMap<Platform::String^, Platform::Object^> ^parameters;
```

**String Constants (for ease of use when setting keys for custom parameters):**

```
static property Platform::String ^TARGET_PARAMETER_ORDER_ID { 
  Platform::String ^get() { return L"orderId"; } 
} 
static property Platform::String ^TARGET_PARAMETER_ORDER_TOTAL { 
  Platform::String ^get() { return L"orderTotal"; } 
} 
static property Platform::String ^TARGET_PARAMETER_PRODUCT_PURCHASE_ID { 
  Platform::String ^get() { return L"productPurchasedId"; } 
} 
static property Platform::String ^TARGET_PARAMETER_CATEGORY_ID { 
  Platform::String ^get() { return L"categoryId"; } 
} 
static property Platform::String ^TARGET_PARAMETER_MBOX_3RDPARTY_ID { 
  Platform::String ^get() { return L"mbox3rdPartyId"; } 
} 
static property Platform::String ^TARGET_PARAMETER_MBOX_PAGE_VALUE { 
  Platform::String ^get() { return L"mboxPageValue"; } 
} 
static property Platform::String ^TARGET_PARAMETER_MBOX_PC { 
  Platform::String ^get() { return L"mboxPC"; } 
} 
static property Platform::String ^TARGET_PARAMETER_MBOX_SESSION_ID { 
  Platform::String ^get() { return L"mboxSession"; } 
} 
static property Platform::String ^TARGET_PARAMETER_MBOX_HOST { 
  Platform::String ^get() { return L"mboxHost"; } 
}
```

<table id="table_AD066582C8E2478A8DC0A59B78ACB443"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Method </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>LoadRequest </p> <p>winJS: loadRequest </p> </td> 
   <td colname="col2"> <p>Sends <span class="codeph"> request </span> to your configured Target server and returns the string value of the offer generated in a block <span class="codeph"> callback </span>. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&nbsp;Windows::Foundation::IAsyncOperation&lt;Platform::String&nbsp;^&gt;&nbsp;^LoadRequest(TargetLocationRequest&nbsp;^request);

    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
ADB.Target.loadRequest(heroBannerRequest).then(function(content)&nbsp;{ 
     
&nbsp;&nbsp;//&nbsp;do&nbsp;something&nbsp;with&nbsp;content&nbsp;returned&nbsp;from&nbsp;target&nbsp;server 
     
}); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> CreateRequest <p>winJS: createRequest </p> </td> 
   <td colname="col2"> <p>Creates a <span class="codeph"> TargetLocationRequest </span> object with the given parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;TargetLocationRequest&amp;nbsp;^CreateRequest(Platform::String&amp;nbsp;^name,&amp;nbsp;Platform::String&amp;nbsp;^defaultContent,&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
var&nbsp;heroBannerRequest&nbsp;=&nbsp;ADB.Target.createRequest("heroBanner",&nbsp;"default.png",&nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CreateOrder​ConfirmRequest </p> <p>winJS: createOrder​ConfirmRequest </p> </td> 
   <td colname="col2"> <p>Creates a <span class="codeph"> TargetLocationRequest </span> object with the given parameters. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;TargetLocationRequest&amp;nbsp;^CreateOrderConfirmRequest(Platform::String&amp;nbsp;^name,&amp;nbsp;Platform::String&amp;nbsp;^orderId,&amp;nbsp;Platform::String&amp;nbsp;^orderTotal,&amp;nbsp;Platform::String&amp;nbsp;^productPurchasedId,&amp;nbsp;Windows::Foundation::Collections::IMap&lt;Platform::String^,&amp;nbsp;Platform::Object^&gt;&amp;nbsp;^parameters); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      var&nbsp;ADB&nbsp;=&nbsp;ADBMobile; 
     
var&nbsp;orderConfirm&nbsp;=&nbsp;ADB.Target.createOrderConfirmRequest("orderConfirm",&nbsp;"order",&nbsp;"47.88",&nbsp;"3722",&nbsp;null); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ClearCookies <p>winJS: clearCookies </p> </td> 
   <td colname="col2"> <p>Clears Target cookies for the application on current device. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;void&amp;nbsp;ClearCookies(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      ADBMobile.Target.clearCookies(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetPcId <p>winJS: getPcId </p> </td> 
   <td colname="col2"> <p>Returns the PC ID cookie for the current device. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Platform::String&amp;nbsp;^GetPcId(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      auto&amp;nbsp;pcId&amp;nbsp;=&amp;nbsp;ADBMobile.Target.getPcId(); 
    </codeblock> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> GetSessionId <p>winJS: getSessionId </p> </td> 
   <td colname="col2"> <p>Returns the Session ID cookie for the current device. </p> <p> <b>Syntax:</b> </p> 
    <codeblock class="syntax csharp">
      static&amp;nbsp;Platform::String&amp;nbsp;^GetSessionId(); 
    </codeblock> <p> <b>Example:</b> </p> 
    <codeblock class="syntax javascript">
      auto&amp;nbsp;sessionId&amp;nbsp;=&amp;nbsp;ADBMobile.Target.getSessionId(); 
    </codeblock> </td> 
  </tr> 
 </tbody> 
</table>

