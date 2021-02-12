<template>
   <view class="container">
<!--      <text-and-button></text-and-button>-->
<!--      <images></images>-->
<!--      <fancy-button></fancy-button>-->
<!--      <location></location>-->
      <push-notifications></push-notifications>
   </view>
</template>

<script>
import Images from "./components/Images";
import TextAndButton from "./components/TextAndButton";
import FancyButton from "./components/FancyButton";
import Location from "./components/Location";
import PushNotifications from "./components/PushNotifications";

export default {
   components: {
      Images,
      TextAndButton,
      FancyButton,
      Location,
      PushNotifications
   },
   data() {
      return {
         //...
      };
   },
   methods: {
      //...
   },
};
</script>

<style>
.container {
   flex: 1;
   background-color: white;
   align-items: center;
   justify-content: center;
}
</style>
