<template>
  <div id="app">
    <div class="box">你好！</div>
    <h1>{{ num }}</h1>
    <button @click="num++">点击+1</button>
  </div>
</template>

<script>
// Vue的生命周期  更新阶段，视图发生变化更新时
// beforeUpdate ==> 视图发生变化更新 ==> updated
export default {
  data() {
    return {
      msg: 'hello',
      num: 0
    }
  },
  methods: {
    fn() {}
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
  }
}
</script>

<style></style>
