<template>
    <div class="container">
        <ul>
            <li v-for="btn_title in btn_titles" :key="btn_title">{{ btn_title }}</li>
        </ul>
    </div>
</template>

<script>
export default {
name: 'side-bar',
data() {
    return {
      btn_titles: ['Image 1', 'Image 2', 'Image3'],
    }
  }
}
</script>

<style scoped lang="scss">
.container{
    width: 20%;
    height: 100%;
    background-color: red;
    display: flex;
    align-items: center;
    justify-content: center;
    li{
        background-color: white;
        margin-bottom: 1rem;
        padding: 1rem;
        font-size: 20px;
    }
}
</style>