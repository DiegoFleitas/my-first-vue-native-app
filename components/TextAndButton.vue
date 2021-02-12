<template>
   <view>
      <text class="text-color-primary">{{ message }}</text>
      <button title="Press me!" @press="exclaim" />
   </view>
</template>

<script>
export default {
   name: "TextAndButton",
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
}
</script>

<style scoped>
.text-color-primary {
   color: blue;
   font-size: 30;
}
</style>
