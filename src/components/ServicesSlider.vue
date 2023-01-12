<template>
  <div>
    <div class="social-stream-carousel">
      <div
        class="carousel-item cursor-pointer"
        v-for="(item, index) in exampleData"
        :key="index"
        :style="{ '-webkit-clip-path': item.clipPath }"
      >
        <div class="image-container">
          <img :src="item.full_picture" alt="" />
        </div>
        <div class="carousel-item-info">
          <img src="example-1.jpg" alt="Eye icon" class="carousel-item-eye-icon" />
          <p class="carousel-item-description">
            {{ item.message && `${item.message.substr(0, 150)}...` }}
          </p>
        </div>
      </div>
    </div>
    <div class="carousel-scrollbar">
      <div class="carousel-scrollbar-thumb"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      exampleData: [
        {
          id: 1,
          full_picture: "example-1.jpg",
          message: "Example item 1",
          clipPath: "polygon(0 0, 100% 0, 100% 85%, 0 100%)",
        },
        {
          id: 2,
          full_picture: "example-2.jpg",
          message: "Example item 2",
          clipPath: "polygon(0 0, 100% 0, 100% 85%, 0 100%)",
        },
        {
          id: 3,
          full_picture: "example-3.jpg",
          message: "Example item 3",
          clipPath: "polygon(0 0, 100% 0, 100% 85%, 0 100%)",
        },
        {
          id: 3,
          full_picture: "example-3.jpg",
          message: "Example item 3",
          clipPath: "polygon(0 0, 100% 0, 100% 85%, 0 100%)",
        },
        {
          id: 3,
          full_picture: "example-3.jpg",
          message: "Example item 3",
          clipPath: "polygon(0 0, 100% 0, 100% 85%, 0 100%)",
        },
        {
          id: 3,
          full_picture: "example-3.jpg",
          message: "Example item 3",
          clipPath: "polygon(0 0, 100% 0, 100% 85%, 0 100%)",
        },
        {
          id: 3,
          full_picture: "example-3.jpg",
          message: "Example item 3",
          clipPath: "polygon(0 0, 100% 0, 100% 85%, 0 100%)",
        },
        // Add more items here as necessary
      ],
    };
  },
  mounted() {
    // Select the carousel container element
    const carousel = this.$el.querySelector(".social-stream-carousel");

    // set the width to 100%
    carousel.style.width = "100%";
    carousel.style.overflowX = "scroll";
  },
};
</script>

<style>
.social-stream-carousel {
  display: flex;
}
.carousel-item {
  flex: 0 0 20%;
  margin-right: 2rem;
}
.image-container img {
  width: 100%;
}

/* Add styles for the scrollbar */
.carousel-scrollbar {
  width: 100%;
  height: 8px;
  background: transparent;
  position: relative;
}

.carousel-scrollbar-thumb {
  height: 8px;
  width: 8px;
  background: #999;
  position: absolute;
  border-radius: 4px;
  top: 0;
  transition: background 0.2s ease-in-out;
}

.carousel-scrollbar::-webkit-scrollbar-thumb {
  background-color: #999;
  border-radius: 4px;
}

/* Add the following to match the size of the thumb with the size of the items */
.carousel-scrollbar::-webkit-scrollbar {
  width: 0.5rem;
}
</style>
