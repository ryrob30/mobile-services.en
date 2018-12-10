---
description: You can route users to a destination depending on whether they have the app installed (an app deep link) or not installed (to a website or an app store).
keywords: mobile
seo-description: You can route users to a destination depending on whether they have the app installed (an app deep link) or not installed (to a website or an app store).
seo-title: Interstitials
solution: Marketing Cloud,Analytics
title: Interstitials
topic: Metrics
uuid: 7dce8ab2-2a5d-4384-ac1e-e31dfaa33654
index: y
internal: n
snippet: y
---

# Interstitials{#interstitials}

You can route users to a destination depending on whether they have the app installed (an app deep link) or not installed (to a website or an app store).

The choice of routing is best left to users. Marketers can provide user choices by configuring an interstitial page that shows users the available landing destinations.

To configure an interstitial when [creating a new marketing link](../../../acquisition-main/c-marketing-links-builder/t-create-edit-adobe-links/t-create-edit-adobe-links.md#task_154A125591904CA598DF9391A44C081C): 

1. Click **[!UICONTROL Edit Deep Link Interstitial]**.

   ![](assets/interstitial2.png)

1. Type information in the following fields:

<table id="table_7085BFEFFF454F2CB6E355A85595E0B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Custom HTML</span> </p> </td> 
   <td colname="col2"> <p> Select your custom interstitial HTML page. Custom interstitials is the ability for marketers to customize interstitial landing pages with custom HTML/CSS/JS, which allows you to brand your pages. </p> <p>Here are the requirements for the HTML page: 
     <ul id="ul_BE51B1E694464879955A24FBD1AAE07D"> 
      <li id="li_C4AD1C1598A349F8B8CC4224A45EFB97">Must be an HTML file. </li> 
      <li id="li_A9149F70FB2C49ACB0AA7B29E23E966C">Must contain the <span class="codeph"> %%DEST%%</span> and <span class="codeph"> %%FALLBACK%%</span> placeholders. </li> 
      <li id="li_C4296F798D304A7ABDA6DB015D01505F">The uploaded HTML will be served in an <span class="codeph"> &lt;iframe&gt;</span>. <p>You must ensure that your link targets are pointing to a parent window. You may include <span class="codeph"> &lt;base target="_parent" /&gt;</span> in <span class="codeph"> &lt;head&gt;</span> or specify a target property for each <span class="codeph"> &lt;a/&gt;</span> individually. </p> </li> 
     </ul> </p> <p> <p>Tip:  If you upload custom HTML, the other four options in this table will not be used unless you remove the uploaded file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Image URL</span> </p> </td> 
   <td colname="col2"> <p>Specify the URL to an image asset. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Body Text </span> </p> </td> 
   <td colname="col2"> <p>Specify the body text for the interstitial. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Confirm Text </span> </p> </td> 
   <td colname="col2"> <p>Specify the text for the text button. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="uicontrol"> Fallback Text </span> </p> </td> 
   <td colname="col2"> <p>Specify the fallback text to display. </p> <p>This field updates the text button if a deep link fails. Users are directed to try the deep link before allowing them to fall back to another option. </p> <p>For example, a fallback could be to an app store to download and install the app or take users to the company's website. The fallback text lets users know that there is another option available if the deep link fails. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Optional) Click the icons above the image to see how the interstitial looks rotated and on different devices.

   You can change or edit the image outside [!DNL Mobile Services] to ensure that the image displays properly in different situations.
1. Click **[!UICONTROL Save]**.
