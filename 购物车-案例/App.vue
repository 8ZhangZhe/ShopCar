<template>
  <div class="app">
    <MyHeader title="购物车案例" color="green" />
    <MyGoods v-for="item in goodsList" :key="item.goods_id" :goods="item" />
    <my-footer :goodsList="goodsList"></my-footer>
  </div>
</template>

<script>
// 1.引入组件 --> 注册组件
// 2.下载bootstrap --> 在main.js引入css样式
import MyHeader from '#/MyHeader.vue'
import MyGoods from '#/MyGoods.vue'
import MyFooter from './components/MyFooter.vue'
// 下载axios，引入axios
// 在App发送请求，传到MyGoods组件进行渲染
import axios from 'axios'
// import MyFooter from '#/MyFooter.vue'
export default {
  // 注册组件
  components: {
    MyHeader,
    MyGoods,
    MyFooter
  },
  data() {
    return {
      goodsList: []
    }
  },
  created() {
    this.getGoods()
  },
  methods: {
    async getGoods() {
      const res = await axios({ url: '/api/cart' })
      this.goodsList = res.data.list
    }
  }
}
</script>

<style scoped>
.app {
  box-sizing: border-box;
  padding: 50px 0;
  max-height: 100vh;
  overflow: auto;
}
</style>
