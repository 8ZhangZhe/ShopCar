<template>
  <div>
    {{ books }}
    <br />
    <input type="text" placeholder="请输入作者" v-model="bookInfo.author" />
    <br />
    <input type="text" placeholder="请输入图书名" v-model="bookInfo.bookname" />
    <br />
    <input
      type="text"
      placeholder="请输入出版社"
      v-model="bookInfo.publisher"
    />
    <button @click="publishBook">发布图书</button>
  </div>
</template>

<script>
// axios全局配置
import axios from 'axios'
// 指定请求时的基础url
//  axios.defaults
// try{} catch() {}  报错执行后面
axios.defaults.baseURL = 'http://123.57.109.30:3006'
axios.defaults.timeout = 3000
export default {
  data() {
    return {
      books: [],
      bookInfo: {
        bookname: '',
        author: '',
        publisher: ''
      }
    }
  },
  created() {
    this.getbooks()
  },
  methods: {
    async getbooks() {
      try {
        const res = await axios({
          url: '/api/getbooks',
          params: {
            bookname: '水浒传'
          }
        })
        console.log(res)
        this.books = res.data.data
      } catch (error) {
        alert('获取图书失败')
      }
    },
    async publishBook() {
      try {
        const res = await axios({
          url: '/api/addbook',
          method: 'POST',
          data: this.bookInfo
        })
        console.log(res)
      } catch (error) {
        alert('添加图书失败')
      }
    }
  }
}
</script>

<style></style>
