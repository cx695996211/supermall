<template>
  <div class="toast" v-show="isShow">{{message}}</div>
</template>

<script>
export default {
  name: "Toast",
  data(){
    return {
      message:'',
      isShow:false
    }
  },
  methods:{
    show(message,duration){
      this.message = message;
      this.isShow = true;
      setTimeout(()=>{
        this.isShow = false;
        this.message = ''
      },duration)
    }
  }
}
</script>

<style scoped>
  .toast{
    position: fixed;
    z-index: 10;
    top:50%;
    left: 50%;
    transform: translate(-50%,-50%);
    background-color: rgba(0,0,0,0.75);
    color: white;
    padding: 8px 10px;
    border-radius: 5px;
  }
</style>