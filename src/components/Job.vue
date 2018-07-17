<template>
      <div class="gray">
        <span class="name">{{name}}</span>
        <el-dropdown class="action" @command="handleCommand">
          <span class="el-dropdown-link">
            Action<i class="el-icon-arrow-down el-icon--right"></i>
          </span>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item command="a">删除</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
        <span class="queue">{{queue}}</span>
        <span class="status">{{status}}</span>
      </div>
</template>

<script>
    export default {
        name: "Job",
        props:['name', 'status', 'queue'],
        methods:{
          handleCommand(){
            console.log("hahha")
          }
        }
    }
</script>

<style scoped>
  .el-dropdown-link {
    cursor: pointer;
    color: #409EFF;
  }
  .el-icon-arrow-down {
    font-size: 12px;
  }
  .gray {
    margin-top: 20px;
  }
  span {
    text-align: center;
    padding-top: 9px;
  }

  .status, .queue, .name, .action{
    display: inline-block;
  }
  .action{
    padding-top:10px;
    padding-left: 6px;
    text-align: center;
  }
  @media screen and (max-width: 638px) {
    .gray{
      height: 100px;
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
      height:100px;
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
    .gray{
      height:50px;
    }
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
    .gray{
      height:50px;
    }
    .name{
      width:30%;
      float: left;
    }
    .action, .status, .queue{
      width:22%;
      float: right;
    }
  }
  @media screen and (min-width: 1065px) {
    .gray{
      height:50px;
    }
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
