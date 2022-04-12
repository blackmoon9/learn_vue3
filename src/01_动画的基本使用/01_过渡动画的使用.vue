<template>
  <div class="app">
    <div>
      <button @click="isShow = !isShow">显示/隐藏</button>
    </div>
    <transition name="msg">
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
    width: 300px;
    margin: 0 auto;
  }
  .title{
    display: inline-block;
  }
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
