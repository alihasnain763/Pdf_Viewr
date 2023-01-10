<template>
  <div>
    <div class="upper-container">
      <div class="main-container">
        <div id="carousel">
          <!-- Canvas element for the current page of the PDF -->
          <div v-for="page in numPages" :key="page">
            <canvas
              v-show="page === currentPage"
              :id="`page-${page}`"
              height="792"
              width="612"
            ></canvas>
          </div>
        </div>
      </div>
      <div class="navigate-btns">
        <button id="prev-btn" v-show="currentPage !== 1" @click="prevPage">
          <span class="material-symbols-outlined"> navigate_before </span>
        </button>
        <button id="next-btn" v-show="currentPage !== numPages" @click="nextPage">
          <span class="material-symbols-outlined"> navigate_next </span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentPage: 1,
      numPages: 0,
      prevDisabled: true,
      nextDisabled: false,
    };
  },
  methods: {
    mainPdfViewer() {
      var url =
        "https://raw.githubusercontent.com/mozilla/pdf.js/ba2edeae/web/compressed.tracemonkey-pldi-09.pdf";

      // Loaded via <script> tag, create shortcut to access PDF.js exports.
      var pdfjsLib = window["pdfjs-dist/build/pdf"];
      pdfjsLib.GlobalWorkerOptions.workerSrc =
        "//mozilla.github.io/pdf.js/build/pdf.worker.js";

      // Asynchronous download of PDF
      var loadingTask = pdfjsLib.getDocument(url);
      loadingTask.promise.then(
        (pdf) => {
          console.log("pdf", pdf);
          this.numPages = pdf.numPages;

          // Render the current page of the PDF to the canvas
          pdf.getPage(this.currentPage).then((page) => {
            var scale = 1;
            var viewport = page.getViewport({
              scale,
            });

            // Get the canvas element for the current page
            var canvas = document.getElementById(`page-${this.currentPage}`);
            var context = canvas.getContext("2d");
            canvas.height = viewport.height;
            canvas.width = viewport.width;

            // Render PDF page into canvas context
            var renderContext = {
              canvasContext: context,
              viewport,
            };
            var renderTask = page.render(renderContext);
            renderTask.promise.then(() => console.log("Page rendered"));
          });
        },
        (reason) => console.error(reason)
      );
    },
    prevPage() {
      if (this.currentPage > 1) {
        this.currentPage -= 1;
        this.prevDisabled = this.currentPage === 1;
        this.nextDisabled = false;
      }
    },
    nextPage() {
      if (this.currentPage < this.numPages) {
        this.currentPage += 1;
        this.prevDisabled = false;
        this.nextDisabled = this.currentPage === this.numPages;
      }
    },
  },
  watch: {
    currentPage: function () {
      this.mainPdfViewer();
    },
  },
  mounted() {
    this.mainPdfViewer();
  },
};
</script>

<style scoped>
/* Container for the carousel */
.mystyle {
  display: block;
}

.mystyle2 {
  display: none;
}

#carousel {
  display: flex;
  overflow-x: hidden;
  overflow-y: hidden;
  justify-content: center;
  align-content: center;
  width: 100%;
  height: 100%;
}

/* .hidden-page { */
/* display: none !important; */
/* } */

/* Canvas elements for each page of the PDF */
#carousel canvas {
  /* margin-right: 2rem; */
  scroll-snap-align: start;
  width: 80%;
  height: 80%;
  padding: 4rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Previous/Next buttons */
#prev-btn,
#next-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  font-size: 24px;
  cursor: pointer;
  user-select: none;
}

/* .navigate-btns{
            position: absolute;
            display: flex;
            justify-content: space-between;
            top: 50%;
            transform: translateY(-50%);
        } */
#prev-btn {
  left: 9rem;
  /* display: none; */
  background-color: transparent;
  border: none;
  color: white;
}

#next-btn {
  right: 9rem;
  background-color: transparent;
  border: none;
  color: white;
}

.material-symbols-outlined {
  font-size: 5rem;
}

/* .main-container {
    margin: 7rem;
    height: 49rem;
    width: 100%;
    display: flex;
    position: relative;
    justify-content: center;
    align-items: center;
    background-color: rgb(61, 54, 54);
}
.upper-container{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-content: center;
    width: 80vw;
    position: relative;  
} */

.upper-container {
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh; /* or any other appropriate height */
}

.main-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 80vw; /* or any other appropriate width */
  height: 80vh; /* or any other appropriate height */
  background-color: rgb(61, 54, 54);
}
</style>
