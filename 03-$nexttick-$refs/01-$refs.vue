<template>
  <div>
    <input type="text" ref="myInput" />
  </div>
</template>

<script>
// 利用 ref 和 $refs 可以用于获取 dom 元素
// 1.收集dom
// 2.DOM元素绑定ref属性，放在$refs
// 4.快捷ID
export default {
  created() {},
  mounted() {
    console.log(this.$refs.myInput)
  }
}
</script>

<style></style>
