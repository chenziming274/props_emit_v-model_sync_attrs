<template>
  <div id="app">
    <el-button type="primary" @click="change(1)">Props</el-button>
    <el-button type="primary" @click="change(2)">自定义事件</el-button>
    <el-button type="primary" @click="change(3)">v-model</el-button>
    <el-button type="primary" @click="change(4)">.sync</el-button>
    <el-button type="primary" @click="change(5)">$attrs与$listeners</el-button>
    <div class="whole">
      <Props v-if="num == 1"></Props>
      <Emit v-if="num == 2"></Emit>
      <Vmodel v-if="num == 3"></Vmodel>
      <Sync v-if="num == 4"></Sync>
      <Attrs v-if="num == 5"></Attrs>
    </div>
  </div>
</template>

<script>
import Attrs from "./components/attrs/index.vue";
import Emit from "./components/emit/index.vue";
import Props from "./components/props/index.vue";
import Sync from "./components/sync/index.vue";
import Vmodel from "./components/vmodel/index.vue";

export default {
  name: "App",
  components: {
    Attrs,
    Emit,
    Props,
    Sync,
    Vmodel
  },
  data() {
    return {
      num:1,
    }
  },
  methods: {
    change(num) {
      if(num == 1) {
        this.num = 1
      } else if(num == 2) {
        this.num = 2
      } else if(num == 3) {
        this.num = 3
      } else if(num == 4) {
        this.num = 4
      } else if(num == 5) {
        this.num = 5
      }
    },
  },
};
</script>

<style>
.whole {
  margin-top: 60px;
  background-color: pink;
  height: 600px;
}
</style>
