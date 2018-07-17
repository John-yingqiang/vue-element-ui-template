<template>
  <el-card >
    <div :class="'card_image ' + title">
      <div :class="class_type"></div>
    </div>
    <div class="card_content">
      <div class="title">{{title}}</div>
      <div class="data">{{detail}}</div>
    </div>
  </el-card>
</template>

<script>
    export default {
        name: "MonitorCard",
        props:["title", "detail", "class_type"],
    }
</script>

<style lang="less" scoped>
.card_image
  {
    display:inline-block;
    width: 82px;
    height: 82px;
    border-radius: 4px;
    text-align: center;
    .icon{
      font-size:40px;
      padding-top:19px;
      color:white;
    }
  }
  .card_content{
    float:right;
    display:inline-block;
    height:82px;
    vertical-align: top;
    .title{
      width:100%;
      height:20px;
      font-size:18px;
      color:rgb(100,100,100);
      text-align: right;
      padding-top:10px;
    }
    .data{
      padding-top:10px;
      width:100%;
      height:40px;
      font-size: 21px;
      font-weight: bold;
      text-align: right;
    }
  }
  .CPU{
    background: -webkit-linear-gradient(left bottom, rgb(253,165,14) , rgb(254,194,25)); /* Safari 5.1 - 6.0 */
    background: -o-linear-gradient(top left, rgb(253,165,14) , rgb(254,194,25)); /* Opera 11.1 - 12.0 */
    background: -moz-linear-gradient(top left, rgb(253,165,14) , rgb(254,194,25)); /* Firefox 3.6 - 15 */
    background: linear-gradient(to top right, rgb(253,165,14) , rgb(254,194,25)); /* 标准的语法 */
  }
  .GPU{
    background: -webkit-linear-gradient(left bottom, rgb(106,202,191) , rgb(129,233,142)); /* Safari 5.1 - 6.0 */
    background: -o-linear-gradient(top left, rgb(106,202,191) , rgb(129,233,142)); /* Opera 11.1 - 12.0 */
    background: -moz-linear-gradient(top left, rgb(106,202,191) , rgb(129,233,142)); /* Firefox 3.6 - 15 */
    background: linear-gradient(to top right, rgb(106,202,191) , rgb(129,233,142)); /* 标准的语法 */
  }
  .Memory{
    background: -webkit-linear-gradient(left bottom, rgb(233,121,66) , rgb(244,118,110)); /* Safari 5.1 - 6.0 */
    background: -o-linear-gradient(top left, rgb(233,121,66) , rgb(244,118,110)); /* Opera 11.1 - 12.0 */
    background: -moz-linear-gradient(top left, rgb(233,121,66) , rgb(244,118,110)); /* Firefox 3.6 - 15 */
    background: linear-gradient(to top right, rgb(233,121,66) , rgb(244,118,110)); /* 标准的语法 */
  }
  .Storage{
    background: -webkit-linear-gradient(left bottom, rgb(66,222,161) , rgb(42,219,223)); /* Safari 5.1 - 6.0 */
    background: -o-linear-gradient(top left, rgb(66,222,161) , rgb(42,219,223)); /* Opera 11.1 - 12.0 */
    background: -moz-linear-gradient(top left, rgb(66,222,161) , rgb(42,219,223)); /* Firefox 3.6 - 15 */
    background: linear-gradient(to top right, rgb(66,222,161) , rgb(42,219,223)); /* 标准的语法 */
  }
</style>
