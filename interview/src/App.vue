<template>
<div class="div">
  <Navbar></Navbar>
  <h1 class="title">History</h1>
  <div class="container"></div>
</div>
</template>

<script>

import Navbar from './components/Navbar.vue'
import {onMounted,ref} from 'vue';
import { inject } from 'vue'
export default {
  
  name: 'App',
  components: {
    
    Navbar
  },
    setup(){
      const axios = inject('axios')
      var arr = ref([])
      console.log(arr.value)
      const getData = () => {
        axios.get('https://api.spacexdata.com/v3/history?limit=9').then((response) => {
          console.log(response.data)
           arr.value = response.data
           console.log(arr.value)
      })
      }
      
      onMounted(()=>{
        getData()
        
      })
      return {
        arr,
        getData
      }
    },
 
}
</script>

<style scoped>

    
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}
.title {
  text-align: center;
}
</style>
