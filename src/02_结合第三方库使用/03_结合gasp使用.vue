<template>
  <div class="app">
    <div>
      <button @click="isShow = !isShow">显示/隐藏</button>
    </div>
    <transition @enter="enter" @leave="leave" :css="false">
      <h2 class="title" v-if="isShow">Hello jack！！！！</h2>
    </transition>
  </div>
</template>

<script>

import gsap from 'gsap'
export default {
  name: 'App',
  data(){
    return{
      isShow:true
    }
  },
  methods:{

    enter(el,done){
      gsap.from(el,{
        scale:0,
        x:-300,
        onComplete:done
      })
    },
    leave(el,done){
      gsap.to(el,{
        scale:1,
        x:200,
        onComplete:done
      })
    },

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

</style>
