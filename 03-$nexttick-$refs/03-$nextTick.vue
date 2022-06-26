<template>
  <div>
    <p ref="myp"> {{ num }} </p>
    <button @click="increment">点击+1</button>
  </div>
</template>

<script>
// $nextTick
//  -更新视图下一刻
//  -this.$nextTick(() => {})

// 更新DOM --> 渲染视图（数据发生变化的时候）
export default {
  data() {
    return {
      num: 0
    }
  },
  methods: {
    increment() {
      this.num += 1

      this.$nextTick(() => {
        console.log(this.$refs.myp.innerHTML)
      })
    }
  }
}
</script>

<style></style>
