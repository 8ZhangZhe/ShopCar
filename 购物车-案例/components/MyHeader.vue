<template>
  <div class="my-header" :style="{ background, color }">{{ title }}</div>
</template>

<script>
// 动态传入样式
// v-bind；style="{属性名：父组件传过来的属性值}"
export default {
  // props: ['title', 'background', 'color']
  // {属性名： value}
  // 1.value是一个类型
  // 2.value是一个对象{default:'默认值'，type:'规定的类型'，required: 是否必传布尔值}
  props: {
    title: String,
    background: {
      type: String,
      default: 'gold'
    },
    color: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="less" scoped>
.my-header {
  height: 45px;
  line-height: 45px;
  text-align: center;
  background-color: #1d7bff;
  color: #fff;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 2;
}
</style>
