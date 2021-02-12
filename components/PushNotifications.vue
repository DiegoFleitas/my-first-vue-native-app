<template>
   <view class="container">
      <text>{{ JSON.stringify(token) }}</text>
      <text class="text-color-primary">{{ JSON.stringify(notification) }}</text>
   </view>
</template>

<script>
import Constants from "expo-constants";
import * as Notifications from "expo-notifications";

Notifications.setNotificationHandler({
   handleNotification: async () => ({
      shouldShowAlert: true,
      shouldPlaySound: false,
      shouldSetBadge: false,
   }),
});

async function schedulePushNotification(notification) {
   await Notifications.scheduleNotificationAsync({
      content: {
         title: notification.title,
         body: notification.body,
         data: notification.data,
      },
      trigger: notification.trigger,
   });
}

async function registerForPushNotificationsAsync() {
   let token;
   if (Constants.isDevice) {
      const { status: existingStatus } = await Notifications.getPermissionsAsync();
      let finalStatus = existingStatus;
      if (existingStatus !== 'granted') {
         const { status } = await Notifications.requestPermissionsAsync();
         finalStatus = status;
      }
      if (finalStatus !== 'granted') {
         alert('Failed to get push token for push notification!');
         return;
      }
      token = (await Notifications.getExpoPushTokenAsync()).data;
      console.log(token);
   } else {
      alert('Must use physical device for Push Notifications');
   }

   if (Platform.OS === 'android') {
      Notifications.setNotificationChannelAsync('default', {
         name: 'default',
         importance: Notifications.AndroidImportance.MAX,
         vibrationPattern: [0, 250, 250, 250],
         lightColor: '#FF231F7C',
      });
   }

   return token;
}

export default {
   name: "PushNotifications",
   data() {
      return {
         token: '',
         notification: {
            title: "You've got mail! 📬",
            body: 'Here is the notification body',
            data: { data: 'goes here' },
            trigger: { seconds: 2 },
         }
      };
   },
   methods: {
      //...
   },
   created() {
      this.token = registerForPushNotificationsAsync();
      schedulePushNotification(this.notification);
   }
}
</script>

<style scoped>

</style>
