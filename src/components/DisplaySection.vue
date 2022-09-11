<template>
  <div class="container">
    <div class="main_content">
      <div v-if="selectedPhoto != null">
        <a :href="selectedPhoto.photographerUrl">{{ selectedPhoto.photographer }}</a>
        <img :src="selectedPhoto.src" :alt="selectedPhoto.alt">
      </div>
      <div v-else>
        <a :href="getDefaultImg().photographerUrl">{{ getDefaultImg().photographer }}</a>
        <img :src="getDefaultImg().src" :alt="getDefaultImg().alt">
      </div>
    </div>
  </div>
</template>

<script>
export default {
name: 'display-section',
data(){
  return{
    defaultImg: this.getDefaultImg(),
  }
},
props: {
    selectedPhoto: Object,
    photos: Array
  },
methods: {
  getDefaultImg(){
    return this.photos[0]
  }
}
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
  }
}
</style>