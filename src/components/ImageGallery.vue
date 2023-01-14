<template>
  <!-- <div class="gallery-image-container">
    <div class="jumbo">
      <ul>
        <li v-for="(item, index) in Images" :key="index">
          <img :src="item" :alt="index" />
        </li>
      </ul>
    </div>
  </div> -->

  <ul class="image-gallery">
    <li v-for="(item, index) in Images" :key="index">
      <img :src="item" alt="" />
    </li>
    <!-- other items here -->
  </ul>
</template>

<script>
export default {
  data() {
    return {
      Images: [
        "https://source.unsplash.com/random/?tech,event",
        "https://natureconservancy-h.assetsadobe.com/is/image/content/dam/tnc/nature/en/photos/WOPA160517_D056-resized.jpg?crop=864%2C0%2C1728%2C2304&wid=600&hei=800&scl=2.88",
        "https://source.unsplash.com/random/?tech,eight",
        "https://source.unsplash.com/random/?tech,eight",
        "https://source.unsplash.com/random/?tech,yet",
        "https://natureconservancy-h.assetsadobe.com/is/image/content/dam/tnc/nature/en/photos/WOPA160517_D056-resized.jpg?crop=864%2C0%2C1728%2C2304&wid=600&hei=800&scl=2.88",
        "https://source.unsplash.com/random/?tech,past",
        "https://www.lego.com/cdn/cs/set/assets/blt3be27e7163925b5a/21335-202209-PDP-Hero-XL-Large.jpg?fit=crop&format=jpg&quality=80&width=1600&height=1000&dpr=1",
        "https://source.unsplash.com/random/?tech,crew",
        "https://source.unsplash.com/random/?tech,crew",
        "https://www.lego.com/cdn/cs/set/assets/blt3be27e7163925b5a/21335-202209-PDP-Hero-XL-Large.jpg?fit=crop&format=jpg&quality=80&width=1600&height=1000&dpr=1",
        "https://source.unsplash.com/random/?tech,card",
      ],
    };
  },
  methods: {},
  mounted() {},
};
</script>
<style>
.image-gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.image-gallery > li {
  height: 300px;
}

.image-gallery li img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}

.image-gallery > li {
  flex: 1 1 auto;
}
</style>
