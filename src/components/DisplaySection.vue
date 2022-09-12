<template>
  <div class="container">
    <div class="main_content" v-if="selectedPhoto != null">
      <a :href="selectedPhoto.photographerUrl">{{ selectedPhoto.photographer }}</a>
      <img :src="selectedPhoto.src" :alt="selectedPhoto.alt">
    </div>
    <div class="main_content" v-else>
      <a :href="photos[0].photographerUrl">{{ photos[0].photographer }}</a>
      <img :src="photos[0].src" :alt="photos[0].alt">
    </div>
  </div>
</template>

<script>
export default {
name: 'display-section',
props: {
    selectedPhoto: Object,
    photos: Array
},
}
</script>

<style lang="scss" scoped>
.container{
  height: 80%;
  background-color: royalblue;
  display: flex;
  justify-content: center;
  align-items: center;
  .main_content{
    background-color: white;
    width: 70%;
    height: 70%;
    display: flex;
    flex-direction: column;
  }
}
</style>