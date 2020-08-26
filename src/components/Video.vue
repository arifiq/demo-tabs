<template>
  <div>
    <video class="video" :src="src" controls="true" auto-play="false"
    @start="onstart" @pause="onpause" @finish="onfinish" @fail="onfail"></video>
  </div>
</template>

<style scoped>
  .video {
    width: 630px;
    height: 350px;
    margin-top: 60px;
    margin-left: 60px;
  }
  .info {
    margin-top: 40px;
    font-size: 40px;
    text-align: center;
  }
</style>

<script>
/* eslint-disable */
  export default {
    data () {
      return {
        state: '----',
        src:'./images/mov_bbb.mp4'
      }
    },
    methods:{
      onstart (event) {
        this.state = 'onstart'
      },
      onpause (event) {
        this.state = 'onpause'
      },
      onfinish (event) {
        this.state = 'onfinish'
      },
      onfail (event) {
        this.state = 'onfinish'
      }
    }
  }
</script>
