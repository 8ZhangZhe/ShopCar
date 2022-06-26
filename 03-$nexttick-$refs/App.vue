<template>
  <div>
    <HeiMaZuJian1 />
    哈哈哈
  </div>
</template>

<script>
// name属性
//  -给组件起个名字
//  -在开发者工具当中查看，便于调试
//  -提供使用规范
import SubComponent from '@/components/MySon.vue'
export default {
  components: {
    [SubComponent.name]: SubComponent
  }
}
</script>

<style></style>
