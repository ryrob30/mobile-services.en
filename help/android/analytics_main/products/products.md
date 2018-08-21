---
description: The products variable cannot be set by using processing rules. In the Mobile SDK, you must use a special syntax in the context data parameter to set products on the server call.
keywords: android;library;mobile;sdk
seo-description: The products variable cannot be set by using processing rules. In the Mobile SDK, you must use a special syntax in the context data parameter to set products on the server call.
seo-title: Products Variable
solution: Marketing Cloud,Analytics
title: Products Variable
topic: Developer and implementation
uuid: 8ccf9899-a738-46ba-b4e5-53fabfe5052b
index: y
internal: n
snippet: y
translate: y
---

# Products Variable

To set the *` products`* variable, set a context data key to ` "&&products"`, and set the value by using the syntax that is defined for the *` products`* variable: 

```
javacdata.put("&amp;&amp;products", "Category;Product;Quantity;Price[,Category;Product;Quantity;Price]");
```
For example: 

```
java//create a context data dictionary 
HashMap cdata = new HashMap<String, Object>(); 
 
// add products, a purchase id, a purchase context data key, and any other data you want to collect. 
// Note the special syntax for products 
cdata.put("&&products", ";Running Shoes;1;69.95,;Running Socks;10;29.99"); 
cdata.put("myapp.purchase", "1"); 
cdata.put("myapp.purchaseid", "1234567890"); 
 
// send the tracking call - use either a trackAction or TrackState call. 
// trackAction example: 
Analytics.trackAction("purchase", cdata); 
// trackState example: 
Analytics.trackState("Order Confirmation", cdata);
```
The *` products`* variable is set on the image request, and the other variables are set as context data: 

<a id="fig_F1B61B67BF9C414F909AB860AC1014D6"></a> ![](assets/products-bloodhound.png) 

All context data variables must be mapped by using processing rules: 

<a id="fig_8258BD49B0A94FA28E2AF4D3EC060787"></a> ![](assets/map-products.png) 

You do not need to map the *` products`* variable by using processing rules because this variable is set directly on the image request by the SDK. 
