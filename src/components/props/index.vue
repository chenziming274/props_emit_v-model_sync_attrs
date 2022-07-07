<template>
  <div class="app">
    <h2>我是App组件</h2>
    <button class="btn" data-mytype="100" @click="showChen($event)">点击查看当前写死的属性</button>
    <button class="btn" v-bind:data-mytype="num" @click="showChen($event)">点击查看当前响应式属性</button>
    <!-- <Demo :eat="vegetables"></Demo> -->
    <!-- <Demo></Demo> -->
    <Demo :eat="vegetables" :x="x"></Demo>
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
      num:180,
      x: 1,
      vegetables:"白菜",
      // vegetables:123,
    }
  },
  methods: {
    showChen(event) {
      let mytype = event.currentTarget.dataset.mytype;
      console.log(mytype)
    },
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
  width: 200px;
}
</style>
