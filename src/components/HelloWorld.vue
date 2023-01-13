<template>
  <section class="social-stream-section global-font-size">
    <div class="social-stream-carousel">
      <div ref="carouselViewport" id="carousel" class="carousel-viewport transition">
        <div
          class="carousel-item cursor-pointer transition"
          v-for="(item, index) in socialStreamData"
          :key="index"
        >
          <div class="parent-div">
            <div class="image-container">
              <img :src="item.full_picture" alt="" />
              <div class="overlay">
                <div class="text-service"><h4>Service Buggati</h4></div>
                <div class="text-description">
                  Sunset, also known as sundown, is the daily disappearance of the Sun
                  below the horizon due
                </div>
              </div>
            </div>
          </div>
          <div class="carousel-item-info transition">
            <p class="carousel-item-description">
              {{ item.message && `${item.message.substr(0, 350)}...` }}
            </p>
          </div>
        </div>
      </div>
      <!-- ***** carousal item dot navigation on mobile******* -->
      <div id="dot-navigation" v-if="isMobile">
        <span
          v-for="(item, index) in socialStreamData"
          :key="index"
          @click="scrollToIndex(index)"
          :class="{ active: index === currentIndex }"
        ></span>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "SocialStreamSlice",
  // The array passed to `getSliceComponentProps` is purely optional and acts as a visual hint for you

  data() {
    return {
      isMobile: false,
      currentIndex: 1,
       ITEMS_PER_PAGE: 3.6,
      ALL_ITEMS_SCROLL_WIDTH: 31.17,
      socialStreamData: [
        {
          id: 1,
          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem  deserunt nostrum facere! Accusamus eligendi, aliquid doloribus sapiente id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 2,
          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem  deserunt nostrum facere! Accusamus eligendi, aliquid doloribus sapiente id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 3,
          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem  deserunt nostrum facere! Accusamus eligendi, aliquid doloribus sapiente id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 4,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem  deserunt nostrum facere! Accusamus eligendi, aliquid doloribus sapiente id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 5,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem  deserunt nostrum facere! Accusamus eligendi, aliquid doloribus sapiente id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
        {
          id: 6,

          message:
            "hello 123 Lorem ipsum dolor sit, amet consectetur adipisicing elit. Repellendus voluptate voluptatem quidem  deserunt nostrum facere! Accusamus eligendi, aliquid doloribus sapiente id ipsa numquam voluptates illum iusto voluptate explicabo incidunt totam cupiditate? from message",
        },
      ],
    };
  },
  mounted() {
    this.scrollToIndex(0)
    this.addWindowResizeEventListener()
    this.checkScreenWidth()
    if (window.innerWidth < 630) {
      this.isMobile = true;
    }
    window.matchMedia("(max-width: 630px)").addListener((event) => {
      this.isMobile = event.matches;
    });
  },

  methods: {
    // *********show  just one item in the DOM
    // scrollToIndexOnMobile(index) {
    //   this.currentIndex = index;
    //   const carousel = document.querySelector("#carousel");
    //   console.log(carousel, index, "button clieck");
    //   carousel.scrollTo({
    //     left: index * carousel.offsetWidth,
    //     behavior: "smooth",
    //   });
    // },
    scrollToIndex(index) {
      this.currentIndex = index
      const carousel = this.$refs.carouselViewport
      carousel.style.transform = `translateX(-${this.ALL_ITEMS_SCROLL_WIDTH * index}%)`
    },
    addWindowResizeEventListener() {

      window.addEventListener("resize", () => {
        this.checkScreenWidth()
      });


      },

      checkScreenWidth() {
      if (window.innerWidth < 599) {
        this.ITEMS_PER_PAGE = 1.4
        this.ALL_ITEMS_SCROLL_WIDTH = 72.62
      }

      if (window.innerWidth > 599 && window.innerWidth < 900) {
        this.ITEMS_PER_PAGE = 2.5
        this.ALL_ITEMS_SCROLL_WIDTH = 41.6
      }

      if (window.innerWidth > 900) {
        this.ITEMS_PER_PAGE = 3.6
        this.ALL_ITEMS_SCROLL_WIDTH = 31.17
      }

      },

  },
};
</script>

<style scoped>

.global-font-size {
    font-size: 10px;
  }

#dot-navigation {
  display: flex;
  justify-content: center;
  margin-top: 65rem;
  position: absolute;
  color: blue;
  z-index: 9999;
  width: 100%;
  height: 2.6rem;
  align-items: center;
}

#dot-navigation span {
  display: inline-block;
  width: 1.3rem;
  height: 1.3rem;
  background-color: rgb(90, 72, 72);
  border-radius: 50%;
  margin: 0 0.25rem;
  cursor: pointer;
  z-index: 999;
}
#dot-navigation span.active {
  background-color: rgb(36, 25, 25);
}
.social-stream-carousel {
  margin-top: 14.4rem;
  display: flex;
  justify-content: end;
  overflow-x: hidden;
  overflow-y: hidden;
  position: relative;
  height: 118.4rem;
}

.social-stream-carousel .carousel-viewport {
  display: flex;
  height: 60%;
  width: 80%;
  position: relative;
  margin: 3.2rem;
  padding: 4.8rem;
  float: left;
  left: 0;
  overflow: hidden;
  transform: translateX(0);
  pointer-events: fill;
  cursor: grab;
  -ms-overflow-style: none;
  scrollbar-width: none;
}
.social-stream-carousel .carousel-viewport .carousel-item {
  flex: 0 0 calc(100% / 3.6);
  /* show 3 items per row */
  position: relative;
  width: 27.77%;
  height: auto;

  /* margin: 0 2.5rem 0 2.5rem; */
}
.carousel-item {
  max-width: 31.8rem;
  min-width: 31.8rem;
}
.overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100%;
  width: 100%;
  opacity: 1;
  transition: 0.5s ease;
  background-color: #0900ba76;
  cursor: pointer;
}

.carousel-item:hover .overlay {
  opacity: 1;
}
.text-service {
  color: white;
  font-size: 1.6rem;
  position: absolute;
  top: 38%;
  left: 40%;
  -webkit-transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
  transform: translate(-50%, -50%);
  text-align: start;
  width: 50%;
}
.text-description {
  color: white;
  font-size: 1.6rem;
  position: absolute;
  top: 60%;
  left: 50%;
  -webkit-transform: translate(-60%, -60%);
  -ms-transform: translate(-60%, -60%);
  transform: translate(-60%, -60%);
  text-align: start;
  width: 60%;
}
.parent-div {
  background: url("https://www.lego.com/cdn/cs/set/assets/blt3be27e7163925b5a/21335-202209-PDP-Hero-XL-Large.jpg?fit=crop&format=jpg&quality=80&width=1600&height=1000&dpr=1");
  /* max-width: 28rem; */
  max-height: 36.6rem;
  min-height: 36.6rem;
  /* object-fit: cover; */
  overflow: hidden;
  position: relative;
  margin: 1rem;
}
.social-stream-carousel .carousel-viewport .carousel-item .parent-div .image-container {
  /* background: url("https://cdn.pixabay.com/photo/2016/11/29/05/45/astronomy-1867616__340.jpg"); */
  max-width: 100%;
  max-height: 70%;
  margin: auto;
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  clip-path: polygon(50% 0, 100% 23%, 100% 77%, 50% 100%, 0 77%, 0 23%);
}
.social-stream-carousel
  .carousel-viewport
  .carousel-item
  .parent-div
  .image-container
  img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.social-stream-carousel .carousel-viewport .carousel-item .carousel-item-info {
  margin-top: 0rem;
  padding-top: 0rem;
  text-align: start;
}
::-webkit-scrollbar {
  width: 0.3rem;
  background-color: transparent;
}
.carousel-viewport::-webkit-scrollbar {
  position: absolute;
  right: 0;
  top: 0;
  bottom: 0;
}

::-webkit-scrollbar-thumb {
  background-color: #818b99;
  border: 0.3rem solid transparent;
  border-radius: 0.9rem;
  background-clip: content-box;
}
::-webkit-scrollbar-thumb:hover {
  background: #9e9e9e;
}
::-webkit-scrollbar {
  height: 2rem;
}

::-webkit-scrollbar-thumb {
  background-color: rgb(227, 235, 10);
}

::-webkit-scrollbar-track-piece:end {
  margin-right: 1.6rem;
}
::-webkit-scrollbar-track-piece:start {
  margin-left: 88rem;
}

.social-stream-carousel
  .carousel-viewport
  .carousel-item
  .carousel-item-info
  .carousel-item-description {
  margin-top: 0.2rem;
  font-family: sans-serif;
  font-size: 1.6rem;
  font-weight: 400;
  max-width: 29.12rem;
  min-width: 29.12rem;
  /* line-height: 1.2rem; */
  color: black;
  padding-left: 1.6rem;
}

@media only screen and (min-width: 630px) {
  .social-stream-carousel {
    overflow: auto;
    height: 112rem;
  }
  .carousel-item:nth-child(odd) {
  /* position every odd numbered item up by 1rem */
    margin-top: 9.6rem;
}
  .carousel-viewport {
    overflow: auto !important;
  }
  .social-stream-carousel .carousel-viewport .carousel-item {
    /* flex: 0 0 calc(100% / 1.4); */
    max-width: 31.8rem;
    min-width: 31.8rem;
  }
  .social-stream-carousel .carousel-viewport .carousel-item .image-container {
    width: 100%;
    height: 42.8rem;
  }
  .social-stream-carousel .carousel-viewport .carousel-item .carousel-item-info {
    opacity: 1;
    margin-top: 0.84rem;
    padding-top: 0.31rem;
    max-width: 36rem;
  }
  .social-stream-carousel
    .carousel-viewport
    .carousel-item
    .carousel-item-info
    .carousel-item-eye-icon {
    width: 3.84rem;
    height: 2.56rem;
  }
  .social-stream-carousel
    .carousel-viewport
    .carousel-item
    .carousel-item-info
    .carousel-item-description {
    margin-top: 0.2rem;
    font-family: sans-serif;
    font-size: 1.6rem;
    font-weight: 300;
    /* line-height: 1.44; */
    color: black;
  }
}

@media only screen and (max-width: 1200px) {
  ::-webkit-scrollbar-track-piece:start {
    margin-left: 40rem;
  }
}
@media only screen and (max-width: 900px) {
  ::-webkit-scrollbar-track-piece:start {
    margin-left: 16rem;
  }
}
@media only screen and (min-width: 400px) {
  .social-stream-carousel {
    margin-top: 6.72rem;
    height: 124.8rem;
  }
}
@media only screen and (max-width: 550px) {
  .carousel-item {
  max-width: 30rem;
  min-width: 30rem;
}
.parent-div{
  height: 38.6rem;
  margin: 2rem;
}

.social-stream-carousel .carousel-viewport .carousel-item .carousel-item-info .carousel-item-description
{
    max-width: 31.68rem;
    min-width: 31.68rem;
}
.social-stream-carousel .carousel-viewport {

  height: 70%;
  width: 70%;
  overflow: hidden;

}
}

</style>
