<template>
  <div id="app">
    <side-bar></side-bar>
    <main>
      <DisplaySection ></DisplaySection>
      <NavBar></NavBar>
      
    </main>
  </div>
</template>

<script>
import axios from "axios"
import DisplaySection from './components/DisplaySection.vue'
import SideBar from './components/SideBar.vue'
import NavBar from './components/NavBar.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    SideBar,
    DisplaySection
  },

  data() {
    return {
      apiUrl: 'https://api.pexels.com/v1/search?query=nature&per_page=1',
      apiKey: '563492ad6f917000010000017f488949f5c24f7cb9fc4ad4069c1050',
      arrImgs: [],
    }
  },
  
  methods: {
    getImage() {
      axios.get(this.apiUrl, {headers: {'Authorization': this.apiKey}})
      .then(response => {
        console.log(response);
        this.arrImgs = response.data.results;
      })
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
