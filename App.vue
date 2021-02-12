<template>
   <view class="container">
      <text class="text-color-primary">{{ message }}</text>
      <button title="Press me!" @press="exclaim" />
      <image
          :source="require('./assets/favicon.png')"
      />
      <image
          :style="{width: 50, height: 50}"
          :source="{uri: 'https://facebook.github.io/react-native/docs/assets/favicon.png'}"
      />
      <image
          :style="{width: 66, height: 58}"
          :source="{uri: 'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADMAAAAzCAYAAAA6oTAqAAAAEXRFWHRTb2Z0d2FyZQBwbmdjcnVzaEB1SfMAAABQSURBVGje7dSxCQBACARB+2/ab8BEeQNhFi6WSYzYLYudDQYGBgYGBgYGBgYGBgYGBgZmcvDqYGBgmhivGQYGBgYGBgYGBgYGBgYGBgbmQw+P/eMrC5UTVAAAAABJRU5ErkJggg=='}"
      />
   </view>
</template>

<script>
export default {
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
