<template>
  <div class="wrapper">
    <h1>MIP 2.0 component example2</h1>
    <h3>This is my first custom component !</h3>
    <p>{{ message }}</p>
  </div>
</template>

<style scoped>
.wrapper {
  margin: 0 auto;
  text-align: center;
}
</style>
<script>
import axios from 'axios'
export default {
  data () {
    return {
      message: 'hello world!'
    }
  },
  mounted () {
    // axios.get('')
    console.log('This is my first custom component !')
  }
}
</script>
