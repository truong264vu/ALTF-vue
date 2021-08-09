<template>
  <div class="timeAnswer" >
       <div class="timeOut" >
       
           <label id="seconds">{{questions[count].timeAnswer}}</label>
       </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
    name:'timeAnswer' ,
    computed:mapState(['questions','count'])
            
    

}
</script>

<style>
    .timeAnswer {
        color: white;
    }
    .timeAnswer .timeOut {
        width: 50px;
        height: 50px;
        border: 5px solid white;
        border-radius: 25px;
    }
    .timeAnswer .timeOut label {
        text-align: center;
        line-height: 50px;
        font-size: 25px;
        
    }
    .timeAnswer .timeOf {
        color: white;
    }

@media (min-width: 100px) and (max-width: 1200px) {
        .timeAnswer .timeOut {
        width: 60px;
        height: 60px;
        border: 5px solid white;
        border-radius: 25px;
    }
    .timeAnswer .timeOut label {
        text-align: center;
        line-height: 60px;
        font-size: 30px;
        
    }
}
    
</style>