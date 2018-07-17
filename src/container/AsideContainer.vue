<template>
    <el-aside class="aside" :width="width" >
      <div class="title" v-show="status">Lenovo Cryo-EM</div>
      <div class="space"></div>
      <div class="home"><span class="icon iconfont icon-home"></span><span v-show="status">　Home</span></div>
      <div class="help"><span class="icon iconfont icon-help"></span><span v-show="status">　Help</span></div>
    </el-aside>
</template>

<script>
    export default {
        name: "Aside",
        props:['vm'],
        data(){
          return {
            status:true,
          }
        },
        computed:{
          width(){
            if(this.status){
              return "230px"
            }
            else{
              return "60px"
            }
          }
        },
        mounted(){
          this.vm.$on("changed",(flag=>{
              this.status = !this.status
          }))
        },
    }
</script>
<style>

</style>
<style scoped >
  .aside{
    background-color: rgb(44,49,55);
    color:#fff;
    transition: width 1s;
  }
  .space{
    height:20px;
  }
  .title{
    height: 35px;
    font-size: 20px;
    color:#fff;
    border-bottom: 1px solid rgb(54,59,65);
    text-align: center;
    padding-top: 12px;
  }
  .home, .help{;
    width: 91.3%;
    height: 35px;
    text-align: center;
    margin:0 auto;
    font-size:14px;
    color:#fff;
    padding-top: 12px;
    cursor: pointer;
  }

  .home:hover, .help:hover{
    border: 1px solid rgb(49,138,255);
    border-radius: 5px;
    background-color: rgb(49,138,255);
  }
  .icon{
    font-size:20px;
  }
</style>
