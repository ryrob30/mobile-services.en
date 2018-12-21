---
description: Here is the list of Adobe Target methods that are provided by the Android library.
keywords: android;library;mobile;sdk
seo-description: Here is the list of Adobe Target methods that are provided by the Android library.
seo-title: Android Target Methods for Adobe Mobile Services
solution: Marketing Cloud,Analytics
title: Target Methods for Android
topic: Developer and implementation
uuid: 8e9808b2-ba80-4646-ba05-8e62d4fde065
---

# Target Methods for Android{#target-methods}

Here is the list of Adobe Target methods that are provided by the Android library.

The SDK currently supports multiple [!DNL Adobe Experience Cloud Solutions], including [!DNL Analytics], [!DNL Target], [!DNL Audience Manager], and the [!DNL Experience Cloud ID Service]. Methods are prefixed according to the solution. For example, Experience Cloud ID methods are prefixed with `target`.

>[!TIP]
>
>[Lifecycle Metrics](../metrics.md#concept_77CA5CEB51D1418FB98EC7C044682A05) are sent as parameters to each mbox load.

## Class Reference : TargetLocationRequest {#section_A8CC898922164E819EC730DC92A6742B}

**Properties:**

```java
public String name; 
public String defaultContent; 
public HashMap<String, Object> parameters;
```

**String Constants**

>[!TIP]
>
>The following constants are for ease of use when you set keys for custom parameters.

```java
public static final String TARGET_PARAMETER_ORDER_ID   = "orderId"; 
public static final String TARGET_PARAMETER_ORDER_TOTAL         = "orderTotal"; 
public static final String TARGET_PARAMETER_PRODUCT_PURCHASE_ID = "productPurchasedId"; 
public static final String TARGET_PARAMETER_CATEGORY_ID         = "categoryId"; 
public static final String TARGET_PARAMETER_MBOX_3RDPARTY_ID    = "mbox3rdPartyId"; 
public static final String TARGET_PARAMETER_MBOX_PAGE_VALUE     = "mboxPageValue"; 
public static final String TARGET_PARAMETER_MBOX_PC             = "mboxPC"; // pcId in cookie 
public static final String TARGET_PARAMETER_MBOX_SESSION_ID     = "mboxSession"; // sessionId in cookie 
public static final String TARGET_PARAMETER_MBOX_HOST           = "mboxHost";
```

>[!IMPORTANT]
>
>* If you are using SDKs **before** version 4.14.0, see [https://developers.adobetarget.com/api/#input-parameters](https://developers.adobetarget.com/api/#input-parameters) for parameters limitations. 
>
>* If you are using SDKs version 4.14.0 **or after**, see [https://developers.adobetarget.com/api/#batch-input-parameters](https://developers.adobetarget.com/api/#batch-input-parameters) for parameters limitations. 

### loadRequest

Sends request to your configured Target server and returns the string value of the offer that is generated in a block callback.

**Syntax:**

```
public static void loadRequest(TargetLocationRequest request, TargetCallback<String> callback);
```

**Example:**

```
Target.loadRequest(heroBannerRequest, new Target.TargetCallback<String>() {  @Override  public void call(String item) {   // do something with item  } });
```

**Syntax:**

```java
public static void loadRequest(final String name, final String defaultContent, final Map `<String, Object>` profileParameters, final Map `<String, Object>` orderParameters,
                                final Map `<String, Object>` mboxParameters, final TargetCallback<String> callback)
```

**Example:**

```java
Map `<String, Object>` profileParameters = new HashMap `<String, Object>`(); profileParameters.put(“profile-parameter-key”, “profile-parameter-value”); Map `<String, Object>` orderParameters = new HashMap `<String, Object>`(); orderParameters.put(“order-parameter-key”, “order-parameter-value”);

Map `<String, Object>` mboxParameters = new HashMap `<String, Object>`(); mboxParameters.put(“mbox-parameter-key”, “mbox-parameter-value”); Target.loadRequest(“mboxName”, “defaultContent”, profileParameters, orderParameters, mboxParameters,  new TargetCallback<String>() {
       @Override     public void call (String item) {
          Log.d(“Target Content”, item); 
     } });
```

### loadRequest

Sends request to your configured Target server and returns the string value of the offer that is generated in a block callback .

**Syntax:**

```java
public static void loadRequest(final String name, final String defaultContent, final Map `<String, Object>` profileParameters, final Map `<String, Object>` orderParameters, 
                               final Map `<String, Object>` mboxParameters, final TargetCallback<String> callback)
```

**Example:**

```java
Map `<String, Object>` profileParameters = new HashMap `<String, Object>`(); profileParameters.put(“profile-parameter-key”, “profile-parameter-value”); 

Map `<String, Object>` orderParameters = new HashMap `<String, Object>`(); orderParameters.put(“order-parameter-key”, “order-parameter-value”); 

Map `<String, Object>` mboxParameters = new HashMap `<String, Object>`(); mboxParameters.put(“mbox-parameter-key”, “mbox-parameter-value”); Target.loadRequest(“mboxName”, “defaultContent”, profileParameters, orderParameters, mboxParameters,  new TargetCallback<String>() {     
  
   @Override 
       public void call (String item) {
             Log.d(“Target Content”, item);
       } });
```

### loadRequest

Sends a request to your configured Target server and returns the string value of the offer that is generated in a TargetCallback.

**Syntax:**

```java
public static void loadRequest(final String name, final String defaultContent, final Map<String, Object> profileParameters, final Map<String, Object> orderParameters, final Map<String, Object> mboxParameters, final Map<String, Object> requestLocationParameters, final TargetCallback<String> callback);
```

**Returns:** N/A

**Parameters:**

|Name: |Description: |
|--- |--- |
|name|****Type:**** String<br>Name of the Target mbox/location that you want to retrieve.|
|defaultContent|**Type:** String<br>Value returned in the callback if the Target server is unreachable, or the user does not qualify for the campaign.|
|profileParameters|**Type:** Map `<String, Object>` <br>Values in this dictionary will go in the "profileParameters" object in the request to Target.|
|orderParameters|**Type:** Map `<String, Object>` <br>Values in this dictionary will go in the "order" object in the request to Target.|
|mboxParameters|**Type:** Map `<String, Object>` <br>Values in this dictionary will go in the request to Target.|
|requestLocationParameters|**Type:** Map `<String, Object>` <br>Values in this dictionary will go in the "requestLocation" object in the request to Target.|
|callback|**Type:** TargetCallback `<String>` <br>This method will be called with the content of the offer from the Target server. If the Target server is unreachable or the user does not qualify for the campaign, defaultContent will be returned.|

**Example:**

```java
Map `<String, Object>` profileParameters = new HashMap `<String, Object>`(); profileParameters.put(“profile-parameter-key”, “profile-parameter-value”); 

Map `<String, Object>` orderParameters = new HashMap `<String, Object>`(); orderParameters.put(“order-parameter-key”, “order-parameter-value”); 

Map `<String, Object>` mboxParameters = new HashMap `<String, Object>`(); mboxParameters.put(“mbox-parameter-key”, “mbox-parameter-value”); 

Map `<String, Object>` requestLocationParameters = new HashMap `<String, Object>`(); requestLocationParameters.put(“request-location-parameter-key”, “request-location-parameter-value”); 

Target.loadRequest(“mboxName”, “defaultContent”, profileParameters, orderParameters, mboxParameters, requestLocationParameters,new TargetCallback<String>() {
       @Override 
       public void call (String item) { 
           Log.d(“Target Content”, item);
       } });
```

For more information about the underlying Target API, see [Delivery](https://docs.adobe.com/dev/products/target/reference/delivery.html) in the Target Developer's help.

### createOrder​ConfirmRequest

Creates a TargetLocationRequest object with the given parameters.

**Syntax:**

```java
public static TargetLocationRequest createOrderConfirmRequest(String name, String orderId, String orderTotal, String productPurchasedId, Map<String, Object> parameters);
```

**Example:**

```
TargetLocationRequest orderConfirm = Target.createOrderConfirmRequest("orderConfirm", "order", "47.88", "3722", null);
```

### createRequest

```
Creates a TargetLocationRequest object with the given parameters.
```

**Syntax:**

```
public static TargetLocationRequest createRequest(String name, String defaultContent, Map<String, Object> parameters);
```

**Example:**

```
TargetLocationRequest heroBannerRequest = Target.createRequest("heroBanner", "default.png", null);
```

### clearCookies

```
Clears any target cookies from your app.
```

**Syntax:**

```
public static void clearCookies();
```

**Example:**

```
Target.clearCookies();
```

### getPcID

Returns the pcID.

**Syntax:**

```
public static String getPcID();
```

**Example:**

```
Target.getPcID();
```

### getSessionID

Returns the session ID.

**Syntax:**

```
public static String getSessionID();
```

**Example:**

```
Target.getSessionID();
```

### setThirdPartyID

Sets the third-party ID.

**Syntax:**

```
public static String setThirdPartyID(final String thirdPartyId);
```

**Example:**

```
Target.setThirdPartyID(“third-party-id”);
```

### getThirdPartyID

Returns the third-party ID.

**Syntax:**

```
public static String getThirdPartyID();
```

**Example:**

```
String thirdPartyId = Target.getThirdPartyID();
```
