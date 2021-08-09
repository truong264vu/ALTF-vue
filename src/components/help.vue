<template>
  <div class="help">
      <form action="">
                            <input type="submmit" value="50/50"  readonly @click="help50($event)" @mousedown.once="HELP_50()">
                            <input type="submmit" value="100%"   readonly @click="help100($event)" @mousedown.once="HELP_100()">
                            <input type="submmit" value="Stop" @click="STOP_GAME()">
                       
      </form>
  </div>
</template>

<script>
// import {mapState} from 'vuex'
import {mapMutations} from 'vuex' 
export default {
    name: 'help' ,
    // computed: mapState(['help50']),
    methods:{ ...mapMutations(['HELP_100','HELP_50','STOP_GAME']),
        help50 (evt) {
            var el = evt.target
            // var help50check = document.getElementById('help50')
            setTimeout(() => {
                el.classList.add('abc')
            },1000)
            
        },
        help100 (evt) {
            var el = evt.target
            // var help50check = document.getElementById('help50')
            setTimeout(() => {
                el.classList.add('abc')
            },1000)
            
        }
    }
    
}
</script>

<style scoped>
    .help input {
        width: 100px;
        height: 60px;
        border: 5px 20px solid white;
        border-radius: 40px;
        text-decoration: none;
        color: white;
        font-size: 25px;
        background: rgb(27, 103, 175);
        text-align: center;
        margin: 40px 20px ;
        outline: none;

    }
    .help input:hover {
        background: green;
        cursor: pointer;
        height: 56px;
        font-size:30px;
    }
   .help .abc {
        background: black;
        color: red;
        outline: none;
    }
    .help .abc:hover {
        background: black;
        cursor: default;
        
    }
    
</style>