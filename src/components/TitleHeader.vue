<template>
  <el-row  class="my-row" :gutter="40" style="margin: 0">
    <el-col :span="24">
      <div class="margin_top">
        <img :src="title_src"/>
      </div>
    </el-col>
  </el-row>
</template>

<script>
    export default {
        name: "TitleHeader",
        props:["title_src"]
    }
</script>

<style scoped>
  .my-row{
    width: 100%;
  }
  .margin_top{
    margin-top:27px;
  }
</style>
