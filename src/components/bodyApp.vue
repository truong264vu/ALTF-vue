<template>
  <div class="body">
         <meta name="viewport" content="width=device-width, initial-scale=1">
      <div class="left">
          <div class="pointtime">
              <div class="point"><point /></div>
              <div class="timeOut"><timeAnswer /> </div>
            </div>
          <div class="question"><question /></div>
      </div>
      <div class="right">
          <div class="help"><help /></div>
          <div class="listPoint"><listPoint /></div>
      </div>
  </div>
</template>

<script>
import question from './question.vue'
import help from './help.vue'
import listPoint from './listPoint.vue'
import point from './point.vue'
import timeAnswer from './timeAnswer.vue'
export default {
    name: 'bodyApp',
    components: {
        question,
        help,
        listPoint,
        point,
        timeAnswer,
    }
}
</script>

<style scoped>
.body {
    display: flex;
    height: 880px;     
}
    .body .left{
        width: 1400px;
        height: 880px;
        border-right: 5px solid wheat;
        margin: 0px auto;
        background: url(../../images/ALTF.jpg) no-repeat  ;
        background-size: 1400px 880px ;
  
    }
    .body .right {
        width: 480px;
        border-right: 10px solid wheat;
        height: 880px;
        background: url(../../images/bgListPoint.jpg) no-repeat  ;
        background-size: 505px 880px ;
    }
    .body .listPoint {
        margin-top: 10px ;
    }
    .body .question {
        margin-top: 100px ;
    }
    .body .pointtime {
        display: flex;
        justify-content: space-around;
        margin-top: 50px;
    }


 
</style>