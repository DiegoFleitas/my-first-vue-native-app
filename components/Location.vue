<template>
   <view class="container">
      <touchable-opacity :on-press="getLocation">
         <text class="text-field-title">Get Location</text>
      </touchable-opacity>
      <text class="text-field-title">Location Object:</text>
      <text>{{ location }}</text>
      <text class="text-field-title">Latitude Only:</text>
      <text>{{ latitude }}</text>

      <text class="text-error">{{ errorMessage }}</text>
   </view>
</template>

<script>
import * as Location from "expo-location";
import * as Permissions from "expo-permissions";

export default {
   data: function() {
      return {
         location: {},
         latitude: "",
         errorMessage: ""
      };
   },
   methods: {
      getLocation: function() {
         Permissions.askAsync(Permissions.LOCATION)
             .then(status => {
                if (!status.granted) {
                   this.errorMessage = "Permission to access location was denied";
                } else if (status.granted) {
                   Location.getCurrentPositionAsync({}).then(location => {
                      this.location = location;
                      this.latitude = location.coords.latitude
                      this.errorMessage = "";
                   });
                }
             })
             .catch(err => {
                console.log(err);
             });
      }
   }
};
</script>

<style>
.container {
   background-color: white;
   align-items: center;
   justify-content: center;
   flex: 1;
}
.text-color-primary {
   color: blue;
}
</style>
