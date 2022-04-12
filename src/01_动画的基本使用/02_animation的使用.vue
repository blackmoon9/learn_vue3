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
  .msg-enter-active{
    animation: bounce 1s ease;
  }
  .msg-leave-active{
    animation: bounce 1s ease reverse;
  }
  @keyframes bounce {
    0%{
      transform: scale(0);
    }
    50%{
      transform: scale(1.2);
    }
    100%{
      transform: scale(1);
    }
  }
</style>
