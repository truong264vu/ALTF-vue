<template>
  <div class="listPoint">
      <meta name="viewport" content="user-scalable=no,width=device-width" />
      <div  class="reverse-list">
          <ul v-for="(list , index ) in questions" :key="index"    
          >
              <li  
              :class="{
                  true: questions[index].point == totalPoint
              }"   
              > 
               {{list.point}}
            </li>
        </ul>
      </div>
  </div>
</template>

<script>
import {  mapState } from 'vuex'
export default {
    name: 'listPoint',
    computed: mapState(['questions','count','totalPoint']),
                // ...mapGetters(['Total2'])},
}
</script>

<style scoped>
 .listPoint ul li {
     list-style: none;
     font-size: 25px;
     color: white;
     width: 280px;
     margin: -20px 0 0 70px;
     border: 3px solid white;
     border-bottom: 3px solid rgb(126, 156, 156);
     border-radius:20px ;
     
 }
 /* dao nguoc li  */
 .reverse-list {
    display: flex; 
    flex-direction: column-reverse;
}
.listPoint .true {
    background: yellow;
    color: black;
    font-size: 25px;
}
/* RPS */


</style>