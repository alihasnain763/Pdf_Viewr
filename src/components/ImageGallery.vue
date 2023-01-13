<template>
    <div>
        <div class="gallery-image-container">
            <div class="image-gallery" >
                
            <img
            v-for="(item, index) in Images" :key="index"
             :src="item" :alt="index">
           
            </div>

        </div>
    </div>
</template>

<script>
export default {
    data(){
        return{
            Images: [
                
                    "https://www.lego.com/cdn/cs/set/assets/blt3be27e7163925b5a/21335-202209-PDP-Hero-XL-Large.jpg?fit=crop&format=jpg&quality=80&width=1600&height=1000&dpr=1",
                    "https://thumbs.dreamstime.com/b/night-landscape-colorful-milky-way-yellow-light-mountains-starry-sky-hills-summer-beautiful-universe-space-72956059.jpg",
                    "https://www.lego.com/cdn/cs/set/assets/blt3be27e7163925b5a/21335-202209-PDP-Hero-XL-Large.jpg?fit=crop&format=jpg&quality=80&width=1600&height=1000&dpr=1",
                    "https://natureconservancy-h.assetsadobe.com/is/image/content/dam/tnc/nature/en/photos/WOPA160517_D056-resized.jpg?crop=864%2C0%2C1728%2C2304&wid=600&hei=800&scl=2.88",
                    "https://www.lego.com/cdn/cs/set/assets/blt3be27e7163925b5a/21335-202209-PDP-Hero-XL-Large.jpg?fit=crop&format=jpg&quality=80&width=1600&height=1000&dpr=1",
                    "https://www.lego.com/cdn/cs/set/assets/blt3be27e7163925b5a/21335-202209-PDP-Hero-XL-Large.jpg?fit=crop&format=jpg&quality=80&width=1600&height=1000&dpr=1",
                    "https://www.lego.com/cdn/cs/set/assets/blt3be27e7163925b5a/21335-202209-PDP-Hero-XL-Large.jpg?fit=crop&format=jpg&quality=80&width=1600&height=1000&dpr=1",
                
            ]
        }
    }
}
</script>
<style>

.gallery-image-container{
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
}
.image-gallery {
  display: flex;
  flex-wrap: wrap;
  
  justify-content: space-around;
  /* align-items: space-betw; */

}

.image-gallery img {
  height: 34.7rem;
  /* width: 100%; */
  max-width: 1200px;
  object-fit: contain;
  margin: 1.5rem;
}


</style>