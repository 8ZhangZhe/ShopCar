<template>
  <div>11</div>
</template>

<script>
// vue的钩子函数
// --特定的时间去调用的函数

// 1.初始化阶段
// -初始化阶段Vue做了什么？ --> 初始化了data,props,methods...

// 2.初始化的两个钩子：
// beforCreate 初始化之前调用的钩子
// created 初始化之后调用的钩子

// 3.在data评级的地方调用
export default {
  data() {
    return {
      msg: 'hello'
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
  }
}
</script>

<style></style>
