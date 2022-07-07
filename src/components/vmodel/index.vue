<template>
  <div class="app">
    <input type="text" v-model="sport">
    <h2>我喜欢{{sport}}</h2>

    <!-- v-model 只是一个指令,他是由 v-bind 单向数据绑定 +@input原生事件实时监听 -->
    <input type="text" :value="sport" @input="sport = $event.target.value">
    <h2>我喜欢{{sport}}</h2>
    <!-- v-model基本上用于表单类元素 -->
    <!-- 那我们尝试用于组件标签呢? -->

    <!-- 
      在html标签中 value是数据单向绑定
      在组件标签中 value就变成了props传值
      @input事件是原生事件
      在组件中变成了自定义事件
     -->

    <!-- <Demo :value="sport" @input="sport = $event"></Demo> -->

    <Demo v-model="sport"></Demo>

    <el-input v-model="sport"></el-input>
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
      sport:"踢足球"
    }
  },
}
</script>

<style>
.app {
  margin-top: 60px;
  background-color: pink;
  text-align: center;
}
</style>
