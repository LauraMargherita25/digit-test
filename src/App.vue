<template>
  <div id="app">
    <SideBar></SideBar>
    <main>
      <Gallery></Gallery>
      <NavBar></NavBar>
    </main>
  </div>
</template>

<script>
import Gallery from './components/Gallery.vue'
import SideBar from './components/SideBar.vue'
import NavBar from './components/NavBar.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    SideBar,
    Gallery
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
