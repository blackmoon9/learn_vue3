<template>
  <div class="app">
    <div>
      <button @click="isShow = !isShow">显示/隐藏</button>
    </div>
    <transition enter-active-class="animate__animated animate__slideInRight"
                leave-active-class="animate__animated animate__slideOutRight">
      <h2 class="title" v-if="isShow">Hello jack！！！！</h2>
    </transition>
  </div>
</template>

<script>


export default {
  name: 'App',
  data(){
    return{
      isShow:true
    }
  }
}
</script>

<style scoped>
.app{
  width: 250px;
  margin: 0 auto;
  overflow: hidden;
}
.title{
  display: inline-block;
}

/*.msg-enter-active{*/
/*  animation: rubberBand 1s ease;*/
/*}*/
/*.msg-leave-active{*/
/*  animation: rubberBand 1s ease reverse;*/
/*}*/

</style>
