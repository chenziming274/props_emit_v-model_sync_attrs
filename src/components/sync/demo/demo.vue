<template>
  <div class="demo">
    <h2>我是demo子组件</h2>
    <button @click="$emit('update:money',money - 100)">花100元</button>
    <h2>爸爸还剩下{{money}}元</h2>
  </div>
</template>

<script>
export default {
  name:"d_demo",
  data() {
    return {
      
    }
  },
  props:["money"]
}
</script>

<style>
.demo{
  background-color: #666;
  margin: 20px;
}
</style>