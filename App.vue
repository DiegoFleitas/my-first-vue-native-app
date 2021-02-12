<template>
   <view class="container">
      <text class="text-color-primary">{{ message }}</text>
      <button title="Press me!" @press="exclaim" />
      <images></images>
   </view>
</template>

<script>
import images from "./components/Images";

export default {
   components: {
      images
   },
   data() {
      return {
         message: "Hello World"
      };
   },
   methods: {
      exclaim() {
         this.message += "!";
      },
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
.text-color-primary {
   color: blue;
   font-size: 30;
}
</style>
