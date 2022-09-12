<template>
    <div class="container">
        <ul>
            <li v-for="btn in arrBtn" :key="btn" @click="$emit('btnIndex', getIndexBtn(btn))">
                {{ btn }}
            </li>
        </ul>
    </div>
</template>

<script>
export default {
name: 'side-bar',
data() {
    return {
      arrBtn: ['Image 1', 'Image 2', 'Image 3',]  
    }
  },
  methods: {
    getIndexBtn(btn){
        return this.arrBtn.indexOf(btn)
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
        cursor: pointer;
    }
}
</style>