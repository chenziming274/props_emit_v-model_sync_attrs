<template>
  <div class="app">
    <h2>我是App组件</h2>
    <h3>我不会任何运动</h3>
    <h4>孩子教会我{{sport1}}</h4>
    <!-- 给子组件绑定自定义事件的第一种写法,通过$refs获取子组件实例对象 -->
    <Demo ref="study"></Demo>
    <!-- 简写形式,vue帮忙进行了简化,本质还是通过$refs获取子组件实例对象 -->
    <!-- <Demo @quxuexi="demo"></Demo> -->
  </div>
</template>

<script>
import Demo from "./demo/Demo.vue";

export default {
  name: "App",
  components: {
    Demo,
  },
  data() {
    return {
      sport1:"",
    }
  },
  methods: {
    demo(a) {
      console.log("有人触发了子组件的事件",a)
      console.log("####",this)
      this.sport1 = a
    }
  },
  mounted() {
    // console.log(this.$refs.study,"获取的子组件实例对象")
    // click 
    // h1 (dom节点) .addEventListener 点击事件 ->回调函数
    // 子组件实例 this.$refs.study $on(当什么什么时候) quxuexi
    // this.$refs.study.$on("quxuexi",function(a) {
    //   console.log("有人触发了子组件的事件",a)
    //   // console.log("####",this)
    //   this.sport1 = a
    // })
    this.$refs.study.$on("quxuexi",this.demo)
  },
};
</script>

<style scoped>
.app {
  text-align: center;
  padding: 10px;
  margin-top: 60px;
  background-color: pink;
}
.btn {
  margin: 10px 10px 50px;
  padding: 20px;
}
</style>
