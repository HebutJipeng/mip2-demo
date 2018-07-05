<template>
  <div class="wrapper">
    <h1>MIP ME</h1>
    <h3>This is my first custom component !</h3>
    <h2>authorizations_url: {{ url }}</h2>
    <mip-img class="demo-img" layout="responsive" src="/static/2018050712241542.png">
    </mip-img>
  </div>
</template>

<style scoped>
.wrapper {
  margin: 0 auto;
  text-align: center;
}
.demo-img {
  height: 100px;
}
</style>

<script>
import request from '../../utils/request'
export default {
  data () {
    return {
      url: ''
    }
  },
  mounted () {
    const self = this
    request.get('').then(res => {
      console.log(res)
      self.url = res.data.authorizations_url
    })
    console.log('This is me')
  }
}
</script>
