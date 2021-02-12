<template>
   <button
       :on-press="onPressLearnMore"
       title="Learn More"
       color="#841584"
       accessibility-label="Learn more about this purple button"
   />
</template>

<script>
export default {
   name: "fancyButton",
   methods: {
      onPressLearnMore: function() {
         alert('Hello')
      }
   }
}
</script>

<style scoped>

</style>
