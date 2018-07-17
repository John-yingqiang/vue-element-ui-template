<template>
  <el-container id="app">
    <Aside :vm="vm"></Aside>
    <MainFrame :vm="vm"></MainFrame>
  </el-container>
</template>

<script>
  import Aside from "./container/AsideContainer"
  import MainFrame from "./container/MainContainer"
  import Vue from "vue";

  let vm = new Vue()

  export default {
      name: 'app',
      data(){
        return {
          vm:vm,
        }
      },
      components:{
        MainFrame,
        Aside,
      }
  }
</script>
<style src="./third_ui_element/icon/iconfont.css"></style>
<style lang="less">
  body{
    margin:0;
    padding:0;
  }

</style>
