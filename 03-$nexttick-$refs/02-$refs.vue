<template>
  <div>
    <MySon ref="son" />
  </div>
</template>

<script>
// $refs
// -收集DOM元素/组件实例
// -收集子组件时干什么用？
// -父子间通讯的方式
//  -props + @自定义事件 + $refs
import MySon from '@/components/MySon.vue'
export default {
  components: { MySon },
  mounted() {
    console.log(this)
    console.log(this.$refs)
    console.log(this.$refs.son)
    console.log(this.$refs.son.msg)
    this.$refs.son.fn()
  }
}
</script>

<style></style>
