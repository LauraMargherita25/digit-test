<template>
  <div class="container">
    <div class="img_container" v-for="photo in photos" :key="photo.alt">
      <img :src="photo.src" :alt="photo.alt">
      <button @click="$emit('select', photo)">Show Me</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'photo-gallery',
  props: {
    photos: [],
  },
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