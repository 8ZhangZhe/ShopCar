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
import axios from 'axios'
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
      const res = await axios({
        url: 'http://123.57.109.30:3006/api/getbooks',
        params: {
          bookname: '水浒传'
        }
      })
      console.log(res)
      this.books = res.data.data
    },
    async publishBook() {
      const res = await axios({
        url: 'http://123.57.109.30:3006/api/addbook',
        method: 'POST',
        data: this.bookInfo
      })
      console.log(res)
    }
  }
}
</script>

<style></style>
