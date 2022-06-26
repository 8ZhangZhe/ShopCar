<template>
  <div>
    {{ books }}
  </div>
</template>

<script>
// axios请求单独某本图书

// 1.params传递查询参数
// 2.async/await
//  - async: 声明一个异步的函数
//  - await: 必须在async函数里面是有，暂停代码执行，等待promise拿到结果

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
    async getbooks() {
      const res = await axios({
        url: 'http://123.57.109.30:3006/api/getbooks',
        params: {
          bookname: '水浒传'
        }
      })
      console.log(res)
      this.books = res.data.data
    }
  }
}
</script>

<style></style>
