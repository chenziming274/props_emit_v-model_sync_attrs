<template>
  <div class="d_demo">
    <h2>我是子组件demo</h2>
    <h3>我会{{sport}}</h3>
    <button @click="help">教父亲踢足球</button>
  </div>
</template>

<script>
export default {
  name: 'D_demo',

  data() {
    return {
      sport:"踢足球"
    }
  },
  methods: {
    help() {
      // console.log(this,"当前子组件的实例对象")
      // console.log(this.$emit("quxuexi"))
      // this.$emit("quxuexi")
      this.$emit("quxuexi",this.sport)
    }
  },
}
</script>

<style scoped>
.d_demo {
  background-color: #666;
  padding: 10px;
}
.span_demo {
  background-color: red;
}
</style>
