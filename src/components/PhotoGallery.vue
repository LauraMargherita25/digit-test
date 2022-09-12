<template>
  <div class="container">
    <div class="img_container" v-for="photo in photos" :key="photo.alt">
      <img :src="photo.srcThumbnail" :alt="photo.alt">
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
  
  background-color: rgb(200, 224, 245);
  padding: 2rem;
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-evenly;
  .img_container{
    width: 280px;
    height: 200px;
  }
}
</style>