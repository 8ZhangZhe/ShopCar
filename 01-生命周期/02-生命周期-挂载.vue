<template>
  <div class="box">你好！</div>
</template>

<script>
// Vue的生命周期
// new Vue() --> beforCreate(){} --> 初始化数据(data，props,methods...开始) --> created(){} --> 挂载阶段 --> 更新阶段 --> 消亡阶段

// beforMount 钩子  ==> 挂载阶段（页面第一次渲染）==> mounted 钩子

// 特性：
// 1.需要在data平级的地方调用声明
// 2.mounted可以拿到真实DOM
// 3.beforMount拿不到真实DOM
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
  },
  beforeMount() {
    console.log('=======================')
    console.log('beforeMount钩子执行了', this.msg, this.fn) // beforeMount钩子执行了 hello ƒ fn() {}
    console.log(document.querySelector('.box')) // null
  },
  mounted() {
    console.log('mounted钩子执行了', this.msg, this.fn) // beforeMount钩子执行了 hello ƒ fn() {}
    console.log(document.querySelector('.box')) // <div>你好</div>
  }
}
</script>

<style></style>
