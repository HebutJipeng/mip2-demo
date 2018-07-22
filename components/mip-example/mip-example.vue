<template>
  <div class="wrapper">
    <h1>MIP 2.0 component example2</h1>
    <h3>This is my first custom component !</h3>
    <p>{{ message }}</p>
    <button on="tap:my-lightbox.toggle" id="btn-open" role="button" tabindex="0">
      Open lightbox
    </button>

    <mip-lightbox
      id="my-lightbox"
      layout="nodisplay"
      class="mip-hidden">
      <div class="lightbox">
          <h1>Hello, World!</h1>
          <p> this is the lightbox</p>
          <span on="tap:my-lightbox.toggle" class="lightbox-close">关闭弹层</span>
      </div>
    </mip-lightbox>
  </div>
</template>

<style>
.wrapper {
  margin: 0 auto;
  text-align: center;
}
.s4s-toast {
  position: fixed;
  top: 10%;
  left: 50%;
  padding: 5px 20px;
  transform: translate(-50%, -50%);
  background-color: rgba(0,0,0,0.7);
  border-radius: 3px;
  color: #fff;
}
</style>
<script>
import axios from 'axios'
import util from '../../utils/toast'

export default {
  data () {
    return {
      message: 'hello world!'
    }
  },
  mounted () {
    util.toast('11')
    console.log(MIP)
    // axios.get('')
    console.log('This is my first custom component !')
  }
}
</script>
