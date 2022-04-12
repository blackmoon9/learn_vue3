<template>
    <div>
      <button @click="addNum">添加数字</button>
      <button @click="removeNum">删除数字</button>
      <button @click="shuffleNum">重新排列</button>
      <transition-group name="my"  tag="p">
        <span class="item" v-for="item in numbers" :key="item" >
          {{item}}
        </span>
      </transition-group>
    </div>
</template>

<script>
import lodash from 'lodash'
export default {
  name: "App",
  data(){
    return{
      numbers:[0,1,2,3,4,5,6,7,8,9],
      numberCounter:10,
    }
  },
  methods:{
    addNum(){
      this.numbers.splice(this.randomIndex(),0,this.numberCounter++)
    },
    removeNum(){
      this.numbers.splice(this.randomIndex(),1)
    },
    randomIndex(){
      return Math.floor(Math.random() * this.numbers.length)
    },
    shuffleNum(){
      this.numbers = lodash.shuffle(this.numbers)
    }
  }
}
</script>

<style scoped>
.item{
  margin: 5px;
  display: inline-block;
}
.my-enter-from,
.my-leave-to{
  opacity: 0;
  transform: translateY(30px);
}

.my-enter-active,
.my-leave-active{
  transition: all 0.5s ease;
}
.my-leave-active{
  position: absolute;
}
.my-move{
  transition: transform 1s ease;
}
button{
  margin: 10px;
}
</style>