<template>
    <div>
        <nav>
  <div class="container">
    <div class="grid">
      <div class="column-xs-12 column-md-10">
        <p id="highlight">Katherine Kato</p>
      </div>
      <div class="column-xs-12 column-md-2">
        <ul>
          <li><a href="#" class="active">Work</a></li>
          <li><a href="#">About</a></li>
        </ul>
      </div>
    </div>
  </div>
</nav>
<section class="gallery">
  <div class="container">
    <div class="grid">
      <div class="column-xs-12 column-md-4">
        <figure class="img-container">
          <img src="https://source.unsplash.com/8b1cWDyvT7Y" />
          <figcaption class="img-content">
            <h2 class="title">Smart Watch</h2>
            <h3 class="category">Showcase</h3>
          </figcaption>
          <span class="img-content-hover">
            <h2 class="title">Smart Watch</h2>
            <h3 class="category">Showcase</h3>
          </span>
        </figure>
      </div>
      <div class="column-xs-12 column-md-4">
        <figure class="img-container">
          <img src="https://source.unsplash.com/5VXH4RG88gc" />
          <figcaption class="img-content">
            <h2 class="title">Camera Film</h2>
            <h3 class="category">Showcase</h3>
          </figcaption>
          <span class="img-content-hover">
            <h2 class="title">Camera Film</h2>
            <h3 class="category">Showcase</h3>
          </span>
        </figure>
      </div>
      <div class="column-xs-12 column-md-4">
        <figure class="img-container">
          <img src="https://source.unsplash.com/XtUd5SiX464">
          <figcaption class="img-content">
            <h2 class="title">Coffee</h2>
            <h3 class="category">Showcase</h3>
          </figcaption>
          <span class="img-content-hover">
            <h2 class="title">Coffee</h2>
            <h3 class="category">Showcase</h3>
          </span>
        </figure>
      </div>
      <div class="column-xs-12 column-md-6">
        <figure class="img-container">
          <img src="https://source.unsplash.com/JYGnB9gTCls" />
          <figcaption class="img-content">
            <h2 class="title">Phone</h2>
            <h3 class="category">Showcase</h3>
          </figcaption>
          <span class="img-content-hover">
            <h2 class="title">Phone</h2>
            <h3 class="category">Showcase</h3>
          </span>
        </figure>
      </div>
      <div class="column-xs-12 column-md-6">
        <figure class="img-container">
          <img src="https://source.unsplash.com/-RBuQ2PK_L8" />
          <figcaption class="img-content">
            <h2 class="title">Keyboard</h2>
            <h3 class="category">Showcase</h3>
          </figcaption>
          <span class="img-content-hover">
            <h2 class="title">Keyboard</h2>
            <h3 class="category">Showcase</h3>
          </span>
        </figure>
      </div>
      <div class="column-xs-12">
        <figure class="img-container">
          <img src="https://source.unsplash.com/P44RIGl9V54" />
          <figcaption class="img-content">
            <h2 class="title">Wrist Watch</h2>
            <h3 class="category">Showcase</h3>
          </figcaption>
          <span class="img-content-hover">
            <h2 class="title">Wrist Watch</h2>
            <h3 class="category">Showcase</h3>
          </span>
        </figure>
      </div>
    </div>
  </div>
</section>

    </div>
</template>


<script>
export default {
   
}
</script>

<style scoped>

@import url('https://fonts.googleapis.com/css?family=Barlow:400,500,700');



body {
  font-family: 'Barlow', sans-serif;
  font-size: 1.125rem;
  line-height: 1.5;

  text-rendering: optimizeLegibility;
}

ul li {
  margin: 0 1.5rem 0 0;
}

a {
  text-decoration: none;
  transition: all 0.2s ease;

}

nav {
  padding: 2.5rem 0 2.5rem 0;

 
}

#highlight {
  font-size: 1.25rem;
}

.gallery {
  padding: 0 0 4rem 0;
}

.img-container {
  width: 100%;
  height: 500px;
  cursor: pointer;
  overflow: hidden;
}

img {
	width: 100%;
  height: 500px;
	object-fit: cover;
  transform: scale(1);
  transition: all 0.3s ease-in-out;

}

.img-content-hover {
  z-index: 1;
  position: absolute;
  top: 0;
  left: 0;
  white-space: nowrap;
  display: none;
  padding: 1rem;
  font-weight: 400;
  margin-top: 1.25rem;
  margin-left: -2rem;
}

.title {
  font-size: 1.5rem;
  font-weight: 700;
}

.category {
  font-size: 1rem;
}

.img-content {
  display: none;
}

.social, .copyright {
  margin: 1rem;
}

.social li {
  display: inline-block;
}



@supports (display: grid) {
  .gallery .grid {
    grid-gap: 1rem;
  }
}
@media(min-width: 540px) {
  nav ul {
    justify-content: flex-end;
  }
}

@media screen and (max-width: 1024px) {
  img:hover {
    transform: none;
  }
  
  .img-container {
    height: 100%;
   
  }

  .img-content {
    display: block;
    padding: 1rem 0;
  }
}

</style>