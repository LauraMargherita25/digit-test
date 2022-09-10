<template>
  <div class="container">
    <div class="main_content">
      <p>Author</p>
      <img src="" alt="">
    </div>
  </div>
</template>

<script>
export default {
name: 'display-section'
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