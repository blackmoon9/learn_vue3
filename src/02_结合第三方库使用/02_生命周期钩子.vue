<template>
  <div class="app">
    <div>
      <button @click="isShow = !isShow">显示/隐藏</button>
    </div>
    <transition @before-enter="beforeEnter"
                @enter="enter"
                @after-enter="afterEnter"
                @before-leave="beforeLeave"
                @leave="leave"
                @after-leave="afterLeave">
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
  },
  methods:{
    beforeEnter(){
      console.log('beforeEnter')
    },
    enter(){
      console.log('enter')
    },
    afterEnter(){
      console.log('afterEnter')
    },
    beforeLeave(){
      console.log('beforeLeave')
    },
    leave(){
      console.log('leave')
    },
    afterLeave(){
      console.log('afterLeave')
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

</style>
