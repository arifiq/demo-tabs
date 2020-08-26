<template>
<div>
  <div class="header-container">
    <text class="title">WeexCompareDemo</text>
  </div>
  <wxc-tab-page ref="wxc-tab-page"
                :tab-titles="tabTitles"
                :tab-styles="tabStyles"
                :tab-page-height="tabPageHeight"
                @wxcTabPageCurrentTabSelected="wxcTabPageCurrentTabSelected">
    <list v-for="(v,index) in tabList"
          :key="index"
          class="item-container"
          :style="{ height: (tabPageHeight - tabStyles.height) + 'px' }">
      <cell class="border-cell"></cell>
      <cell >
        <wxc-pan-item :ext-id="'1-' + (v) + '-' + (key)"
                      @wxcPanItemPan="wxcPanItemPan">
         <component v-bind:is="v.content" class="tab"></component>
        </wxc-pan-item>
      </cell>
    </list>
  </wxc-tab-page>
</div>
</template>

<style scoped>
  .header-container {
    background-color: #673ab7;
  }
  .title {
    color: #ffffff;
    font-size: 32px;
    padding: 30px 30px;
  }
  .item-container {
    width: 750px;
    background-color: #f2f3f4;
  }

  .border-cell {
    background-color: #f2f3f4;
    width: 750px;
    height: 24px;
    align-items: center;
    justify-content: center;
    border-bottom-width: 1px;
    border-style: solid;
    border-color: #e0e0e0;
  }

  .cell {
    background-color: #ffffff;
  }

  .content{
    width:750px;
    height:300px;
    border-bottom-width:1px;
    align-items: center;
    justify-content: center;
  }
</style>
<script>
/* eslint-disable */
  const dom = weex.requireModule('dom');
  import { WxcTabPage, WxcPanItem, Utils, BindEnv } from 'weex-ui';

  // https://github.com/apache/incubator-weex-ui/blob/master/example/tab-page/config.js
  import Config from  './config'
  import Vue from 'vue'

  export default {
    components: { WxcTabPage, WxcPanItem },
    data: () => ({
      tabTitles: Config.tabTitles,
      tabStyles: Config.tabStyles,  
      tabList: Config.tabTitles,
      tabPageHeight: 1334
    }),
    created () {
      this.tabPageHeight = Utils.env.getPageHeight();
      let tabslastIndex =  this.tabList.length;
      console.log("hus",this.tabTitles)
      while(tabslastIndex<=20){
        Vue.set(this.tabList, tabslastIndex, {title: `tab${tabslastIndex}`});
        tabslastIndex++;
      }
      console.log("fhus",this.tabTitles)
    },
    computed: {
      currentTabComponent: function(){
          return ;
      }
    },
    methods: {
      wxcTabPageCurrentTabSelected (e) {
        const self = this;
        const index = e.page;
        /* Unloaded tab analog data request */
        // if (!Utils.isNonEmptyArray(self.tabList[index])) {
        //   setTimeout(() => {
        //     Vue.set(self.tabList, index, self.demoList);
        //   }, 100);
        // }
      },
      wxcPanItemPan (e) {
        if (BindEnv.supportsEBForAndroid()) {
          this.$refs['wxc-tab-page'].bindExp(e.element);
        }
      }
    }
  };
</script>
