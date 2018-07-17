<template>
      <div class="gray job_title">
        <span class="name">Job Name<span class="up el-icon-sort-up"></span><span class="down el-icon-sort-down"></span></span>
        <span class="action">Action<span class="up el-icon-sort-up"></span><span class="down el-icon-sort-down"></span></span>
        <span class="queue">Queue<span class="up el-icon-sort-up"></span><span class="down el-icon-sort-down"></span></span>
        <span class="status">Status<span class="up el-icon-sort-up"></span><span class="down el-icon-sort-down"></span></span>
      </div>
</template>

<script>
    export default {
        name: "JobTitle"
    }
</script>

<style lang="less" scoped>
.gray{
  background-color: rgb(251,251,251);
  .up, .down{
    width:15px;
    padding-left:0;
    padding-right:0;
    cursor: pointer;
  }
  span{
    text-align: center;
    padding-top:9px;
    .up{
      color:rgb(170,170,170);
    }
  }
  .status, .queue, .name, .action{
    display: inline-block;
  }
}
@media screen and (max-width: 638px) {
  .gray{
    height: 50px;
  }
  .name{
    width:50%;
  }
  .status, .queue, .action{
    width:40%;
    float: right;
  }
  .status{
    float: left;
  }
}
@media screen and (min-width: 638px) {
  .gray{
    height:50px;
  }
  .name{
    width:50%;
  }
  .status, .queue, .action{
    width:40%;
    float: right;
  }
  .status{
    float: left;
  }
}
@media screen and (min-width: 697px) {
  .name{
    width:30%;
    float: left;
  }
  .action, .status, .queue{
    width:20%;
    float: right;
  }
}
@media screen and (min-width: 991px) {
  .name{
    width:30%;
    float: left;
  }
  .action, .status, .queue{
    width:23%;
    float: right;
  }
}
@media screen and (min-width: 1065px) {
  .name{
    width:30%;
    float: left;
  }
  .action, .status, .queue{
    width:20%;
    float: right;
  }
}
</style>
