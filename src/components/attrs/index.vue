<template>
  <div id="app">
    <!-- $attrs 和 $listeners -->
    <!-- 当前el-button缺少我想要的功能,需求 鼠标悬停添加文字提示信息,那么此时我就需要二次封装一下button按钮 -->
    <el-button type="primary" icon="el-icon-plus"></el-button>
    <el-button type="danger" icon="el-icon-delete"></el-button>
    <!-- <Btn xxx="123" :yyy="'abc'" @haha="test"></Btn> -->
    <div>
      <br />
      <Btn type="primary" icon="el-icon-plus" title="添加" @haha="test"></Btn>
      <Btn type="danger" icon="el-icon-delete" title="删除" @haha="test"></Btn>
    </div>
  </div>
</template>

<script>
import Btn from "./demo/Btn.vue";

export default {
  name: "App",
  components: {
    Btn,
  },
  methods: {
    test() {},
  },
};
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
