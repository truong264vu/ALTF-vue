
<template>
  <div id="start">
      <meta name="viewport" content="width=device-width, initial-scale=1">
      <!-- <div class="tutorial">
          <p>Chúng tôi có tất cả 15 câu hỏi .<br>
          Bạn có : <br>
          - 30 giây để trả lời mỗi câu hỏi <br>
                    - 2 quyền trợ giúp <br>
                   - 1 quyền dừng chơi</p>
      </div> -->
      <div class="startGame">
            <input type="submit" id="OnStart" value="Bắt đầu" @click="timeOut()" @mousedown.once="hideScreenStart()">         
      </div>
  </div>
</template>

<script>
// import { mapGetters } from 'vuex'
export default {
    name: 'StartPlay',
    // computed: mapGetters(['TIME_OUT']),
    methods: {
        hideScreenStart() {
            document.getElementById("OnStart").onclick = function () {
                document.getElementById("start").style.display = 'none';
            };      
          
        },
        timeOut() 
              {
                  
                setInterval(() => {
                    this.$store.state.questions[this.$store.state.count].timeAnswer--;
                    if(this.$store.state.questions[this.$store.state.count].timeAnswer <= 0){
                        location.reload()
                        alert('Hết thời gian')         
                    }
                    if( this.$store.state.questions[this.$store.state.count].timeAnswer < 10 ) 
                    this.$store.state.questions[this.$store.state.count].timeAnswer
                    = '0' + this.$store.state.questions[this.$store.state.count].timeAnswer;
                },1000)
              }
            
                
    }
        
    
}
</script>

<style scoped>
    #start {
        width: 1910px;
        height: 880px;
        background: url(../../images/dolar.jpg) no-repeat ;
        background-size: 1880px 880px;
      
        
    }
    .hide{
        display: none;
    }
    #start .startGame input {
          position: absolute;
          font-size: 30px;
          background: white;
          color: rgb(80, 22, 12);
          left: 840px;
          top: 580px;
          height: 60px;
          width: 200px;
          border: 3px solid blueviolet;
          border-radius:40px ;
    }
    #start .startGame input:hover {
        height: 70px;
        width: 210px;
        cursor: pointer;
    }

</style>
