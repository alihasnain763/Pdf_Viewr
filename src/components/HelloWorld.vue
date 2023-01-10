<template>
  <div class="video-container">
    <iframe
      width="560"
      height="315"
      src="https://www.youtube.com/embed/Tfaq4UTH7P0"
      title="YouTube video player"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      allowfullscreen
    ></iframe>
  </div>
  <div class="container">
    <iframe
      id="iframe-360"
      src="https://momento360.com/e/u/662eb3d719344370be3aba5373c53f98?utm_campaign=embed&utm_source=other&heading=0&pitch=0&field-of-view=75&size=medium&display-plan=true"
      width="80%"
      height="480"
    ></iframe>
  </div>
</template>

<script>
export default {
  name: "PDFViewer",

  methods: {},
  mounted() {},
};
</script>

<style>
video {
  height: 60vh;
  border: 2px solid black;
}

.logo-anchor {
  display: none !important;
}

.video-container {
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  margin: 2rem;
  height: 100vh;
  width: 100vw;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
