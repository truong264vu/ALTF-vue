<template>
  <div class="slide">
      <input type="submit"  value="prev" @click="COUNT_DOWN" v-show="count > 0">
      <input type="submit" value="next" @click="COUNT_UP" v-show="count < questions.length - 1">


      
  </div>
</template>

<script>
import {mapMutations, mapState} from 'vuex'
export default {
    name: 'slide',
    computed: mapState(['questions','count']),
    methods: mapMutations(['COUNT_UP','COUNT_DOWN'])

        
    
}
</script>

<style scoped>
   
    .slide input {
        width: 120px;
        height: 60px;
        color: white;
        cursor: pointer;
        margin: 5px 300px;
        border-radius:5px ;
        background: rgb(51, 94, 187);
        font-size: 20px;
    }
    .slide input:hover {
        color: white;
        background: rgb(48, 73, 184);
        font-size: 25px;
    }
</style> 