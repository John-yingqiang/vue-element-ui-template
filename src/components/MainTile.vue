<template>
  <el-row>
    <el-col :span="24">
      <div class="title"><span class="icon iconfont icon-foldzhedie"  @click="zoomBook"></span></div>
    </el-col>
  </el-row>
</template>

<script>
    export default {
      name: "MainTile",
      props:["vm"],
      data(){
        return {
          status: true,
        }
      },
      methods:{
        zoomBook(){
          this.status = !this.status;
          this.vm.$emit("changed", this.status);
        }
      }
    }
</script>

<style scoped>
  .title{
    height: 35px;
    font-size: 20px;
    background-color: #fff;
    padding-top: 12px;
    padding-left:12px;
    cursor:pointer;
  }
  .icon{
    font-size: 20px;
  }
</style>
