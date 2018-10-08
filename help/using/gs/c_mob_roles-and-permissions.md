---
description: In Adobe Analytics, you can manage roles on the Admin Tools Home page.
seo-description: In Adobe Analytics, you can manage roles on the Admin Tools Home page.
seo-title: Roles and Permissions
title: Roles and Permissions
uuid: 0fb50cfa-09be-4ab5-9bbb-5da22083dca1
index: y
internal: n
snippet: y
translate: y
---

# Roles and Permissions

In Adobe Analytics, you can manage roles on the Admin Tools Home page.

## Overview {#section_91B8192891E14E5285718C8118912500}

The following roles manage permissions in the Mobile Services UI:

**Analytics Admin**

An Analytics Admin manages user groups and assigns permissions, one of which is the Mobile App Admin. The Experience Cloud Admin links your Adobe ID to your Adobe Analytics account, which allows you to log in to the Mobile Services UI by using your Adobe ID. For more information about the Experience Cloud Administrator, see [Administration - User Management and FAQ](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

>[!TIP]
>
>An existing Analytics Admin has the ability to assign the Analytics Admin role to any user.

For more information about this role, see the following content:

* [Users](https://marketing.adobe.com/resources/help/en_US/reference/users.html) 
* [Frequently Asked Questions - Analytics Permission Changes](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html)

**Mobile App Admin**

This role is the Admin for the Mobile Services UI.

>[!IMPORTANT]
>
>For some features, such as push messaging, the Analytics Admin must select the **[!UICONTROL Segment Creation]** check box in [!UICONTROL User Management].

## Managing Access {#section_E6939C2695AA4A0DBF432D50B2670920}

Here is some additional information about accessing options in the Mobile Services UI:

**Apps and Report Suites**

All Mobile Service apps are tied to report suites. If users do not have access to a report suite, they will not have access to that report suite's associated app.

**Mobile Services and Analytics Features**

If your company does not have an Analytics contract to access a feature in the UI, such as Push Messaging, no user in your company will have access to that feature, regardless of permission level.

## Roles and Permissions {#section_20AA029D5B8C413C8659777E79B11620}

Here are the roles in the Mobile Services UI, with their relevant permissions:

**Analytics Admin**

* All User & Mobile App Admin Permissions 
* Create App with new report suite 
* Delete App from Mobile Services

  >[!IMPORTANT]
  >
  >Although the app has been deleted in the Mobile Services UI, the report suite still exists in Analytics.

* Manage App Settings

    * Enable Lifecycle Reporting 
    * Enable Location Reporting

**Mobile App Admin **

* All User Permissions 
* Create App with existing report suite 
* Manage App Settings

    * Configure App's Mobile SDK options 
    * Configure App's UI settings 
    * Configure linked App Store apps 
    * Configure App's Universal Link options 
    * Configure Push Services certs and API keys 
    * Create/Update/Activate/Deactivate/Duplicate/Archive/Delete Postbacks 
    * Create/Update/Archive/Delete Link Destinations

* Create/Update/Archive Marketing Links 
* Create/Import/Update/Delete Legacy Acquisition Links 
* Create/Import/Update/Delete Places (Points of Interest) configuration 
* Create/Update/Send/Schedule/Cancel/Duplicate/Archive/Delete Push Messages 
* Create/Update/Activate/Deactivate/Duplicate/Archive/Delete In-App Messages

For more information about groups and users, see:

* [Groups](https://marketing.adobe.com/resources/help/en_US/reference/groups.html) 
* [Add a user to a group](https://marketing.adobe.com/resources/help/en_US/reference/t_add_user_to_group.html)

**Mobile Services User**

This role has view-only permissions and can provide feedback in the Mobile Services UI.

* Provide Feedback on Mobile Services UI 
* View Apps

  >[!IMPORTANT]
  >
  >Users can only see the report suites for which they have access in Adobe Analytics.

* View App Settings

    * Download App SDK configuration 
    * View all UI and SDK settings 
    * View Variables & Metrics configuration 
    * View Postbacks 
    * View Link Destinations

* View & Run Reports 
* View Marketing Links 
* View & Export Legacy Acquisition Links 
* View & Export Places (Points of Interest) configuration 
* View Push Messages 
* View In-App Messages

