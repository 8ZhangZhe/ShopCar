<template>
  <div>
    <h1>你好</h1>
  </div>
</template>

<script>
// 体验axios
// 通过 res.data拿到的才是真正服务器返回的数据
// method:默认值是get

import axios from 'axios'
export default {
  created() {
    axios({
      url: 'https://httpbin.org/get',
      method: 'GET',
      params: {
        name: '张三',
        age: 18
      }
    }).then((res) => {
      console.log(res)
    })
  }
}
</script>

<style></style>
