<template>
  <div>
    {{ msg }}
    我是子组件MySon
  </div>
</template>

<script>
export default {
  name: 'HeiMaZuJian1',
  data() {
    return {
      msg: '你好，父组件'
    }
  },
  methods: {
    fn() {
      console.log('hello!')
    }
  }
}
</script>

<style></style>
