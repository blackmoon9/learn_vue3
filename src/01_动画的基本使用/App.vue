<template>
  <button @click="isShow = !isShow">显示/隐藏</button>
  <transition name="msg">
    <h2 v-if="isShow">Hello jack！！！！</h2>
  </transition>
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
  .msg-enter-from,
  .msg-leave-to{
    opacity: 0;
  }
  .msg-enter-to,
  .msg-leave-from{
    opacity: 1;
  }
  .msg-enter-active,
  .msg-leave-active{
    transition: opacity 2s ease;
  }
</style>
