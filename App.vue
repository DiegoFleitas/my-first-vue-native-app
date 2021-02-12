<template>
   <view class="container">
      <text-and-button></text-and-button>
      <images></images>
      <fancy-button></fancy-button>
   </view>
</template>

<script>
import Images from "./components/Images";
import TextAndButton from "./components/TextAndButton";
import FancyButton from "./components/FancyButton";

export default {
   components: {
      Images,
      TextAndButton,
      FancyButton
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
