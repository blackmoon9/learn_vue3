<template>
  <div class="app">
    <input type="number" v-model="counter" step="100">
    <h2>{{showCounter}}</h2>
  </div>
</template>

<script>

import gsap from 'gsap'
export default {
  name: 'App',
  data(){
    return{
      counter:0,
      showNumber:0
    }
  },
  computed:{
    showCounter(){
      return this.showNumber.toFixed(0)
    }
  },
  watch:{
    counter(newVal){
      gsap.to(this,{duration:1,showNumber:newVal})
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
