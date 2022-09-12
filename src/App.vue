<template>
  <div id="app">
    <side-bar @btnIndex="selectPhoto"></side-bar>
    <main>
      <DisplaySection :photos="photos" :selectedPhoto="selectedPhoto"></DisplaySection>
      <PhotoGallery :photos="photos"></PhotoGallery>
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
      this.photos = response.data.photos.map((photo) => ({
        srcThumbnail: photo.src.tiny,
        src: photo.src.landscape,
        alt: photo.alt,
        photographer: photo.photographer,
        photographerUrl: photo.photographer_url,
      })
      );
    })
  },

  methods: {
    selectPhoto(index){
      let i = 0;
      while (i != index) {
        i++;
      }
      this.selectedPhoto = this.photos[index];
    }
  }
}
</script>

<style lang="scss">

@import "./assets/style.scss";

#app {
  font-family: 'Courier New', Courier, monospace;
  height: 100vh;
  display: flex;
  main{
    width: 80%;
    display: flex;
    flex-direction: column;
  }
}
</style>
