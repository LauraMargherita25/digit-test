<template>
  <div class="container">
    <div class="img_container" v-for="photo in photos" :key="photo.alt">
      <img :src="photo.src" :alt="photo.alt">
    </div>
  </div>
</template>

<script>
import axios from "axios"
export default {

  name: 'nav-bar',

  data() {
    return {
      apiUrl: 'https://api.pexels.com/v1/search?query=nature&per_page=3',
      apiKey: '563492ad6f91700001000001777e61cd1d234a07b2d8199d3c161487',
      photos: [],
    }
  },
  
  mounted() {
    axios.get(this.apiUrl, {headers: {'Authorization': this.apiKey}})
    .then(response => {
      console.log(response.data.photos);
      this.photos = response.data.photos.map((photo) => ({
        src: photo.src.tiny,
        alt: photo.alt,
        photographer: photo.photographer,
        photographerUrl: photo.photographer_url
      })
      );
    })
  }
}
</script>

<style lang="scss" scoped>
.container{
  height: 20%;
  background-color: blueviolet;
  padding: 2rem;
  display: flex;
  justify-content: space-evenly;
  .img_container{
    background-color: white;
    width: 200px;
    height: 100%;
    img{
      width: 100%;
    }
  }
}
</style>