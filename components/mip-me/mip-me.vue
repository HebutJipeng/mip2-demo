<template>
  <div class="wrapper">
    <h1>MIP ME</h1>
    <h3>This is my first custom component !</h3>
    <h2>authorizations_url: {{ url }}</h2>
    <mip-img class="demo-img" layout="responsive" src="/static/2018050712241542.png">
    </mip-img>
    <hr>
    <br>
    <div v-for="i in 5">
      <button @click="add(i, i+'_my_value')" class="btn">add+{{i}}</button>
    </div>
    <br>
    <br>
    <br>
    <br>
    <hr>
    <button @click="alert()">输出</button>
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
      url: '',
      sum: []
    }
  },
  mounted () {
    const self = this
    request.get('').then(res => {
      console.log(res)
      self.url = res.data.authorizations_url
    })
    console.log('This is me')
  },
  methods: {
    add(idx, myvalue) {
      var tem = {
        id: idx,
        value: myvalue
      }
      let flag = true,
          flag_id
      this.sum.length !== 0 && this.sum.forEach((item, index) => {
        if(item.value == myvalue) {
          flag = false
          flag_id = index
        }
      })
      if(!flag) {
        console.log('对象中已存在该值，现在删除')
        this.sum.splice(flag_id, 1)
      } else {
        this.sum.push(tem)
      }
      console.log(this.sum)
    },
    alert() {
      let a = this.sum.map((item, idx) =>{
        return item.value
      })
      console.log(a.join('_'))
      // 提交
    }
  }
}
</script>
