<template>
  <el-card  class="card">
    <div class="card_image">
      <div class="image">
        <img :src="image_src"/>
      </div>
    </div>
    <div class="card_content">
      <div class="card_content_detail">{{details}}</div>
      <el-button class="button" plain size="small">Start</el-button>
    </div>
  </el-card>
</template>

<script>
    export default {
        name: "AppCard",
        props:["image_src", "details"]
    }
</script>

<style scoped>
  .card{
    position: relative;
    height: 120px;
    border-radius: 5px;
  }
  .card_image{
    position: absolute;
    top:20px;
    left:5px;
    width: 80px;
    height: 80px;
    border: 1px solid rgb(244,244,244);
    border-radius: 5px;
  }
  .image{
    height: 23px;
    position: absolute;
    left:1px;
    top:25px;
  }
  .card_content{
    position: absolute;
    left: 90px;
    top:20px;
    width: 65%;
    height: 80px;
    overflow:hidden;
  }
  .card_content_detail{
    position:absolute;
    left:5px;
  }
  .button{
    position: absolute;
    top:48px;
    right:0;
  }
</style>
