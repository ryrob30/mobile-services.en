---
description: You can attach image files to your Android notifications. Adding visual components can significantly increase your user's engagement with push notifications.
seo-description: You can attach image files to your Android notifications. Adding visual components can significantly increase your user's engagement with push notifications.
seo-title: Receive Rich Push Notifications
title: Receive Rich Push Notifications
uuid: 4a0340a6-666b-49b6-907a-9afc966dfdba
---

# Receive Rich Push Notifications {#receive-rich-push-notifications}

You can attach image files to your Android notifications. Adding visual components can significantly increase your user's engagement with push notifications.

## Handle the Incoming Rich Push Message (GCM) {#section_AF1A3BC2312C4E1DA517CC90296C11E2}

If the app is in the foreground, the push message will be handled by the app that extends the `GcmListenerService` class and is declared in the manifest file in the following way: 

```java
<service 
    android:name="com.mycompany.MyGcmListenerService" 
    android:exported="false" > 
    <intent-filter> 
        <action android:name="com.google.android.c2dm.intent.RECEIVE" /> 
    </intent-filter> 
</service>
```

>[!IMPORTANT]
>
>The class that contains the `onMessageReceived()` implementation to handle the data that is received.

If the push message contains a Media URL, the URL will be available in the `Bundle` parameter that is passed to the `onMessageReceived()` function. The key to be used is `attachment-url` as shown in the following code sample: 

```java
public class MyGcmListenerService extends GcmListenerService { 
    @Override 
    public void onMessageReceived(String from, Bundle data) { 
 Intent intent = new Intent(this, MainMenuActivity.class); 
intent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP); 
 
//put the data bundle in the intent to track clickthroughs 
intent.putExtras(data); 
 
PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, intent, 
        PendingIntent.FLAG_ONE_SHOT); 
 
Uri defaultSoundUri= RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION); 
 
NotificationCompat.Builder notificationBuilder = new NotificationCompat.Builder(this) 
        .setSmallIcon(R.drawable.icon) 
        .setContentTitle("ADBMobileSamples") 
        .setContentText(message) 
        .setAutoCancel(true) 
        .setSound(defaultSoundUri) 
        .setContentIntent(pendingIntent); 
 
//Handle image url if present in the push message 
String attachmentUrl = data.getString("attachment-url"); 
 
if (attachmentUrl != null) { 
    Bitmap image = getBitmapFromURL(attachmentUrl); 
    if (image != null) { 
        notificationBuilder.setStyle(new NotificationCompat.BigPictureStyle().bigPicture(image)); 
    } 
} 
//Display the Notification 
NotificationManager notificationManager = (NotificationManager)getApplicationContext().getSystemService(Context.NOTIFICATION_SERVICE); 
notificationManager.notify(0, notificationBuilder.build()); 
 
} 
 
}
```

>[!IMPORTANT]
>
>When you set `NotificationCompat.BigPictureStyle`, large images might not be displayed. To ensure that large images are always displayed, set the native `Notification.BigPictureStyle`.

## Sample Rich Push Notification {#section_6819316BEDDE45108413B541CA2BB2DC}

Here is an example of a rich push notification with an image:

![](assets/rich-push-notification_example.png)

For more information about rich push notifications with Android, see [Engage with Rich Notifications](https://developer.android.com/distribute/best-practices/engage/rich-notifications.html). 
