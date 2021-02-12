<template>
   <view class="container">
      <text-and-button></text-and-button>
      <images></images>
   </view>
</template>

<script>
import Images from "./components/Images";
import TextAndButton from "./components/TextAndButton";

export default {
   components: {
      Images,
      TextAndButton
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
</style>
