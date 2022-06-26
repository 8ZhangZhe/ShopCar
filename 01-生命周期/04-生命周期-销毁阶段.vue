<template>
  <div id="app">
    <div class="box">你好！</div>
    <h1>{{ num }}</h1>
    <button @click="num++">点击+1</button>
    <button @click="fn">点击销毁</button>
  </div>
</template>

<script>
// 销毁阶段
// 1. v-if 进行开关切换的时候会启动销毁
// 2.调用 this.$destroy() 的时候，会启动自我销毁Vue
export default {
  data() {
    return {
      msg: 'hello',
      num: 0
    }
  },
  methods: {
    fn() {
      this.$destroy()
    }
  },
  beforeCreate() {
    console.log(this.msg, this.fn) // undefined undefined
    console.log('beforeCreate钩子执行了') // beforeCreate钩子执行了
  },
  created() {
    console.log(this.msg, this.fn) // hello ƒ fn() {}
    console.log('created钩子执行了') // created钩子执行了
  },
  beforeMount() {
    console.log('=======================')
    console.log('beforeMount钩子执行了', this.msg, this.fn) // beforeMount钩子执行了 hello ƒ fn() {}
    console.log(document.querySelector('.box')) // null
    console.log(document.querySelector('#app')) // null
  },
  mounted() {
    console.log('mounted钩子执行了', this.msg, this.fn) // beforeMount钩子执行了 hello ƒ fn() {}
    console.log(document.querySelector('.box')) // <div>你好</div>
  },
  beforeUpdate() {
    console.log('=======================')
    console.log('beforeUpdate钩子执行了') // 页面更新后才打印
  },
  updated() {
    console.log('updated钩子执行了') // 页面更新后才打印
  },
  beforeDestroy() {
    console.log('=======================')
    console.log('beforDestroy钩子执行了')
  },
  destroyed() {
    console.log('destroyed钩子执行了')
  }
}
</script>

<style></style>
