<template>
  <div class="demo">
    <h2>{{value}}</h2>
    <input type="text" :value="value" @input="$emit('input',$event.target.value)">

  </div>
</template>

<script>
export default {
  name:"d_demo",
  props:["value"]
}
</script>

<style>
.demo {
  background-color: #666;
  margin: 20px;
}
</style>