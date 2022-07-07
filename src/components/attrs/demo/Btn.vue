<template>
  <a href="JavaScript:;" :title="title">
    <el-button class="btn" v-bind="$attrs" v-on="$listeners"></el-button>
    <!-- 这里不能简写,这一步代表了将所有的$attrs里面的值绑定给el-button -->
    <!-- 属性通过v-bind进行设置,注意这里不能进行简写, 自定义事件通过v-on进行绑定 -->
  </a>
</template>

<script>
export default {
  name:"b_Btn",
  props:["title"],
  mounted() {
    // this.$attrs就是父组件传递过来的所有属性(除了props接收了的属性以及style和class)组成的对象
    // 如果通过props进行接收了, 那么this.$attrs就接收不到这个属性了
    // this.$listeners 就是父组件传递过来的所有绑定的事件组成的对象
    console.log(this.$attrs,this.$listeners)
  },
}
</script>

<style>
.btn {
  width: 60px;
  height: 50px;
  margin: 20px;
}
</style>