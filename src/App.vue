<template>
  <ImageGallery />
  <!-- <AnotherSlider /> -->
  <!-- <SocialStreamSlice /> -->
</template>

<script>
import ImageGallery from "./components/ImageGallery.vue";
// import AnotherSlider from "./components/AnotherSlider.vue";
// import ShoperPdf from "./components/ShoperPdf.vue";
// import SocialStreamSlice from "./components/ServicesSlider.vue";

export default {
  name: "App",
  components: {
    ImageGallery,
    // AnotherSlider,
    // SocialStreamSlice,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
