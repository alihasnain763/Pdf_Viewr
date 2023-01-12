<template>
  <HelloWorld />
  <!-- <AnotherSlider /> -->
  <!-- <SocialStreamSlice /> -->
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
// import AnotherSlider from "./components/AnotherSlider.vue";
// import ShoperPdf from "./components/ShoperPdf.vue";
// import SocialStreamSlice from "./components/ServicesSlider.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
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
