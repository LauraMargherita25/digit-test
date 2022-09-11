<template>
  <div id="app">
    <side-bar></side-bar>
    <main>
      <DisplaySection :selectedPhoto="selectedPhoto" :photos="photos"></DisplaySection>
      <PhotoGallery :photos="photos" @select="selectPhoto"></PhotoGallery>
    </main>
  </div>
</template>

<script>
import axios from "axios"
import DisplaySection from './components/DisplaySection.vue'
import SideBar from './components/SideBar.vue'
import PhotoGallery from './components/PhotoGallery.vue'

export default {
  name: 'App',
  components: {
    PhotoGallery,
    SideBar,
    DisplaySection
  },

  data() {
    return {
      apiUrl: 'https://api.pexels.com/v1/search?query=nature&per_page=3',
      apiKey: '563492ad6f91700001000001777e61cd1d234a07b2d8199d3c161487',
      photos: [],
      selectedPhoto: null
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
        photographerUrl: photo.photographer_url,
        selected: false
      })
      );
    })
  },

  methods: {
    selectPhoto(photo){
      this.selectedPhoto = photo
    }
  }
}
</script>

<style lang="scss">

@import "./assets/style.scss";

#app {
  height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  display: flex;
  main{
    width: 80%;
    display: flex;
    flex-direction: column;
  }
}
</style>
