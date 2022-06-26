<template>
  <div>
    <h1>你好</h1>
  </div>
</template>

<script>
// 1.下载 yarn add axios
// 2.引入

import axios from 'axios'
export default {
  created() {
    acios({
      url: '',
      method: 'get',
      params: {},
      data: {},
      headers: {}
    })
      .then((res) => {})
      .catch((err) => {
        console.log(err)
      })
  }
}
</script>

<style></style>
