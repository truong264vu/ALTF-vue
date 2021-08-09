<template>
  <div class="question">
          <!-- <link rel='stylesheet' href='https://cdn.rawgit.com/t4t5/sweetalert/v0.2.0/lib/sweet-alert.css'> -->

          <h1>Câu {{count+1}} : {{questions[count].question}} </h1>

                     
              <li 
                
                
                v-for="(nameAnswer,index) in questions[count].answer" 
                :key="index"
                @mousedown="questions[count].choose = index"
                @click="showDelete($event)"   
                :class="{
                    choosed: questions[count].choose == index,
                }"
                         
                >
               {{nameAnswer}}
             </li>
            
        
    </div>
</template>

<script>
import swal from 'sweetalert';
import {mapMutations, mapState} from 'vuex' 
export default {
    name: 'question',
    computed: mapState(['questions','count','totalPoint']),
    // mounted() {
     
    //   let recaptchaScript = document.createElement('script')
    //   recaptchaScript.setAttribute('src', 'https://cdn.rawgit.com/t4t5/sweetalert/v0.2.0/lib/sweet-alert.min.js')
    //   document.head.appendChild(recaptchaScript)
    
    // },
    methods:{
        ...mapMutations(['TOTAL_POINT','STOP_GAME']),  
        showDelete (evt) {
        let el = evt.target
        if(this.$store.state.questions[this.$store.state.count].choose
         == this.$store.state.questions[this.$store.state.count].correct){
             // hiện đáp án đúng
                {
                    setTimeout(() => {
                    el.classList.add('true') 
                }, 2000)
                setTimeout(() => {       
                 alert("Đúng rồi !", {
                    className: "acb",
                })
                     this.$store.state.count  =  this.$store.state.count + 1                          
                },3000)
                }
        }
        //hiện đáp án sai
                else {
                    setTimeout(() => {
                    el.classList.add('false')
                    swal('Sai rồi !', 'đán án : ' + this.$store.state.questions[this.$store.state.count].answer[this.$store.state.questions[this.$store.state.count].correct])
                   
                }, 2000)
                setTimeout(() => {
                    
                     location.reload()
                },5000)
                }
      },
    } 
 }   
</script>

<style scoped>

.question h1 {

    border-radius:50px;
    background: darkblue;
    color: white;
    line-height: 100px;
    width: 1000px;
    height: 160px;
    padding: 30px;
    margin: 50px auto;
    
    
}

@media (hover: hover) {
 
    .question li:hover {
    background: green;
    cursor: pointer;
} 
}
.isCorrect {
    background: rgb(190, 190, 30);

}
.question .choosed {
    background: rgb(118, 150, 56);
}
.question .true {
    background: rgb(125, 226, 43);
}
.question .false {
    background: red;
}

.question li  {

    display: inline-block;
    text-decoration: none;
    text-align:center ;
    color: white;
    line-height: 60px;
    font-size: 30px;
    background: rgb(131, 36, 199);
    vertical-align:top;
    height: 60px;
    width: 500px;
    margin: 20px 20px;
    border-radius: 15px;
    border:  2px solid white; 

}
.correct {
    background: rgb(51, 25, 6);
}
.swal-modal {
  background-color: rgba(63,255,106,0.69);
  border: 3px solid white;
}

@media (min-width: 100px) and (max-width: 1200px) {

.question h1 {

    border-radius:40px;
    background: rgb(29, 29, 165);
    color: white;
    line-height: 80px;
    width: 1000px;
    height: 160px;
    padding: 30px;
    margin: 20px auto;
    
  
}
.question li  {
    line-height: 80px;
    text-align: center;
    font-size: 35px;
    height:80px;
    width: 500px;
    border-radius: 15px;
    border:  2px solid white; 

}
}
</style>