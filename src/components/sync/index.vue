<template>
  <div class="app">
    <h2>我是app父组件</h2>
    <h2>我有{{money}}元</h2>
    <!-- <h2 class="no">不使用sync修饰符</h2> -->
    <!-- :money 通过props 进行传值 @update:money自定义事件 -->
    <!-- 第一种写法中,必须用update:money的这种形式 不能用单个单词的形式 -->
    <!-- <Demo :money="money" @update:money="money = $event"></Demo> -->

    <!-- <h2 class="no">不使用sync修饰符</h2> -->
    <Demo :money.sync="money"></Demo>

  </div>
</template>

<script>
import Demo from './demo/demo.vue'

export default {
  name: 'App',
  components: {
    Demo
  },
  data() {
    return {
      money:1000,
    }
  },
}
</script>

<style>
.app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: pink;
}
</style>
