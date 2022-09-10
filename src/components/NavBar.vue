<template>
  <div class="container">
    <div class="img_container">
      <img src="" alt="">
    </div>

    <div class="img_container">
      <img src="" alt="">
    </div>

    <div class="img_container">
      <img src="" alt="">
    </div>

    <div class="img_container">
      <img src="" alt="">
    </div>
  </div>
</template>

<script>
export default {
name: 'nav-bar'
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
  }
}
</style>