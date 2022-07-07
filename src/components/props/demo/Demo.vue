<template>
  <div class="d_demo">
    <h2>我是子组件demo</h2>
    <button @click="updateX">点击修改当前值</button>
    <!-- <h2>我爱吃{{food}},我有一个{{goods}},我最喜欢的运动{{sport}},<span class="span_demo">我父组件非让我吃???</span></h2> -->
    <h2>我爱吃{{food}},我有一个{{goods}},我最喜欢的运动{{sport}},<span class="span_demo">我父组件非让我吃{{eat}}</span></h2>
    <h1>{{x}}</h1>
    <h1>{{x2}}</h1>
    <!-- <input type="text" v-model="x2"> -->
  </div>
</template>

<script>
export default {
  name: 'D_demo',
  // props的第一种传值方式, 是最完整的写法,对于类型,必要性以及默认值都进行了限制
  // props: {
  //   eat: {
  //     type:String,
  //     default:"苦瓜",
  //     required:true
  //   }
  // },

  // props的第二种传值方式,只对类型进行限制
  props:{
    eat:String,
    x:Number,
  },

  // props第三种传值方式,不对任何进行限制
  // props:["eat"],

  data() {
    return {
      food:"炖肉",
      goods:"牙刷",
      sport:"踢足球",
      x2:"",
    }
  },
  mounted() {
    console.log("子组件demo",this)
    this.x2 = this.x
  },
  methods: {
    updateX() {
      this.x2 = 2
      // this.x = 2
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
