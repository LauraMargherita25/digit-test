<template>
  <div id="app">
    <side-bar></side-bar>
    <main>
      <DisplaySection></DisplaySection>
      <NavBar></NavBar>
    </main>
  </div>
</template>

<script>
import DisplaySection from './components/DisplaySection.vue'
import SideBar from './components/SideBar.vue'
import NavBar from './components/NavBar.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    SideBar,
    DisplaySection
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
