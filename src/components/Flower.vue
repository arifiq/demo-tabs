<template>
  <div class="wrapper">
    <scroller class="scroller">
      <div class="row" v-for="(item, index) in items" :ref="'item'+index" :key="index">
        <image class="image" :src="item.url"></image>
         <text class="text">{{item.name}}</text>
      </div>
    </scroller>
  </div>
</template>

<script>
/* eslint-disable */
  const dom = weex.requireModule('dom')

  export default {
    data () {
      return {
        items: []
      }
    },
    created () {
      for (let i = 1; i < 1000; i++) {
        this.items.push({name: `flower${i}`, url: `./images/flower${i}.jpg`})
      }
    },
  }
</script>

<style scoped>
  .scroller {
    width: 700px;
    /* height: 700px; */
    /* border-width: 3px; */
    /* border-style: solid; */
    /* border-color: rgb(162, 217, 192); */
    /* margin-left: 25px; */
  }
  .row {
    height: 200px;
    flex-direction: row;
    /* justify-content: center; */
    /* border-bottom-width: 2px; */
    /* border-bottom-style: solid; */
    /* border-bottom-color: #DDDDDD; */
  }
  .text {
    font-size: 45px;
    color: #666666;
  }
  .image {
    width: 160px;
    height: 160px;
    resize:both;
}
</style>