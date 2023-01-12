<template>
  <div>
    <div class="social-stream-carousel">
      <div
        ref="carouselViewport"
        class="carousel-viewport"
        @scroll="handleCarouselScroll"
      >
        <div
          class="carousel-item cursor-pointer"
          v-for="(item, index) in socialStreamData"
          :key="index"
        >
          <img :src="item.full_picture" alt="" />
          <div class="carousel-item-info">
            <p>{{ item.message }}</p>
          </div>
        </div>
      </div>
    </div>
    <div class="scrollbar-container">
      <div
        class="scrollbar-handle"
        @mousedown="handleMouseDown"
        @mousemove="handleMouseMove"
        @mouseup="handleMouseUp"
        ref="scrollbarHandle"
      ></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      socialStreamData: [
        {
          id: 1,
          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 2,
          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 3,
          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 4,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 5,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 6,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 6,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 6,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 6,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 6,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 6,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 6,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem exercitationem deserunt nostrum facere corporis! Accusamus eligendi, aliquid doloribus sapiente corporis id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
      ],
      scrollbarHandleWidth: 0,
    };
  },
  // mounted() {
  //   this.updateScrollbarHandleWidth();
  //   window.addEventListener("resize", this.updateScrollbarHandleWidth);
  //   document.addEventListener("mouseup", () => {
  //     document.removeEventListener("mousemove", this.handleMouseMove);
  //   });
  // },
  // beforeUnmount() {
  //   window.removeEventListener("resize", this.updateScrollbarHandleWidth);
  // },

  // methods: {
  //   handleCarouselScroll(event) {
  //     const { scrollLeft, clientWidth, scrollWidth } = event.target;
  //     const percentage = (scrollLeft / (scrollWidth - clientWidth)) * 100;
  //     this.$refs.scrollbarHandle.style.left = `${percentage}%`;
  //   },
  //   handleMouseDown(event) {
  //     this.startX = event.clientX;
  //     this.startWidth = this.$refs.scrollbarHandle.offsetWidth;
  //     document.addEventListener("mousemove", this.handleMouseMove);
  //     document.addEventListener("mouseup", this.handleMouseUp);
  //   },
  //   handleMouseMove(event) {
  //     let handleWidth = this.startWidth + (event.clientX - this.startX);
  //     let handleWidthRight = handleWidth + handleWidth;
  //     let trackWidth = this.$refs.scrollbarTrack.offsetWidth;
  //     if (handleWidth < 0) {
  //       handleWidth = 0;
  //     } else if (handleWidthRight > trackWidth) {
  //       handleWidth = trackWidth - this.$refs.scrollbarHandle.offsetWidth;
  //     }
  //     this.$refs.scrollbarHandle.style.width = `${handleWidth}px`;
  //     this.$refs.carouselViewport.scrollLeft =
  //       (handleWidth / trackWidth) * this.$refs.carouselViewport.scrollWidth;
  //   },

  //   handleMouseUp() {
  //     document.removeEventListener("mousemove", this.handleMouseMove);
  //     document.removeEventListener("mouseup", this.handleMouseUp);
  //   },
  //   updateScrollbarHandleWidth() {
  //     const carouselViewport = this.$refs.carouselViewport;
  //     const scrollbarTrack = this.$refs.scrollbarTrack;
  //     const scrollbarHandle = this.$refs.scrollbarHandle;
  //     const handleWidth =
  //       (carouselViewport.clientWidth / carouselViewport.scrollWidth) *
  //       scrollbarTrack.offsetWidth;
  //     scrollbarHandle.style.width = `${handleWidth}px`;
  //     this.$refs.carouselViewport.scrollLeft =
  //       (handleWidth / scrollbarTrack.offsetWidth) *
  //       this.$refs.carouselViewport.scrollWidth;
  //   },
  // },
};
</script>

<style>
/* Define the container for the carousel */
.carousel-container {
  position: relative;
  overflow: hidden;
  width: 100%;
  height: 100%;
}

/* Define the viewport for the carousel items */
.carousel-viewport {
  display: flex;
  width: 100%;
  height: 100%;
  overflow-x: scroll;
  overflow-y: hidden;
  scroll-snap-type: x mandatory;
}

/* Define the individual carousel items */
.carousel-item {
  flex: 0 0 auto;
  width: 25%;
  height: 100%;
  scroll-snap-align: center;
}

/* Add some basic styling for the carousel items */
.carousel-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Add a custom scrollbar for the carousel */
.scrollbar-container {
  position: absolute;
  bottom: 0;
  right: 0;
  width: 0.5rem;
  height: 100%;
  background-color: #ccc;
}

/* Define the handle for the custom scrollbar */
.scrollbar-handle {
  position: absolute;
  top: 0;
  right: 0;
  width: 0.5rem;
  height: 10%;
  background: #6e6e6e;
  cursor: pointer;
  border-radius: 1rem;
  transition: background 0.2s ease;
}

.scrollbar-handle:hover {
  background: #9e9e9e;
}

.carousel-viewport::-webkit-scrollbar {
  width: 0.5rem;
}

.carousel-viewport::-webkit-scrollbar-thumb {
  background: #6e6e6e;
  border-radius: 1rem;
}

.carousel-viewport::-webkit-scrollbar-thumb:hover {
  background: #9e9e9e;
}
.carousel-viewport::-webkit-scrollbar {
  height: 2rem;
  /* background: red; */
}

.carousel-viewport::-webkit-scrollbar-thumb {
  background-color: blue;
  /* background: red; */
}

.carousel-viewport::-webkit-scrollbar-track-piece:end {
  margin-right: 10rem;
  /* background: red; */
}

.carousel-viewport::-webkit-scrollbar-track-piece:start {
  margin-left: 3rem;
  /* background: red; */
}
</style>
