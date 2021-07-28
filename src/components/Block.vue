<template>
  <div class="block" v-if="showBlock" @click="stopTimer">
      Click Here {{delay}}   
  </div>
</template>

<script>
export default {
    data(){
        return{
            showBlock:false,
            score:0,
            timer:null
        }
    },
    mounted(){
        setTimeout(()=>{
            this.showBlock = true;
            this.startBlockTimer();
        }, this.delay)
    },
    updated(){
        console.log('changed')
    },
    unmounted(){
        console.log('component unmounted')
    },
   props: ['delay'],
   methods:{
       startBlockTimer(){
           this.timer= setInterval(()=>{
               this.score += 50
           },50)
       },
       stopTimer(){
           clearInterval(this.timer)
           this.$emit('endGame',this.score)
     }
   }
}
</script>

<style>
.block{
    background-color: red;
    width: 400px;
    height: 300px;
    margin:20px auto;
    padding-top: 30px;
}
</style>