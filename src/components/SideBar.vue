<template>
    <div class="container">
        <ul>
            <li v-for="btn in btns" :key="btn.name" @click="select">
                <button >{{ btn.name }}</button>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
name: 'side-bar',
data() {
    return {
      btns: [
        {
            name:'Image 1', 
            selected: false
        }, 
        {
            name:'Image 2', 
            selected: false
        }, 
        {
            name:'Image 3', 
            selected: false
        }
        ],
    }
  },
methods:{
    select(){   
         
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
    button{
        background-color: white;
        margin-bottom: 1rem;
        padding: 1rem;
        font-size: 20px;
    }
}
</style>