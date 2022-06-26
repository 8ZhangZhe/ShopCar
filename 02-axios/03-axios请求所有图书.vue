<template>
  <div>
    {{ books }}
  </div>
</template>

<script>
// 请求图书，将图书渲染到页面上

// 1.发送请求: baseURL + url
// 2.服务端返回的数据，res.data
// 3.请求封装成函数，在created中调用

import axios from 'axios'
export default {
  data() {
    return {
      books: []
    }
  },
  created() {
    this.getbooks()
  },
  methods: {
    getbooks() {
      axios({
        url: 'http://123.57.109.30:3006/api/getbooks'
      }).then((res) => {
        console.log(res)
        this.books = res.data.data
      })
    }
  }
}
</script>

<style></style>
