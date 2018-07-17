<template>
  <el-card  class="card" :body-style="{padding:'0px', height:'320px'}">
    <div class="title">
      <p>Running...</p>
    </div>
    <div class="content">
      <div class="card_content">
          <div class="image"><div class="image_content"><img :src="image_src"/></div></div>
          <div class="card_content_detail">{{project_name}}</div>
      </div>
      <div class="params">
        <p>Voltage(KV): <span>300</span></p>
        <p>Spherical Aberration(mm): <span>0.00</span></p>
        <p>Pixel Size(A): <span>1.5000</span></p>
        <p>Exposure per Frame(e-/A2): <span>2.00</span></p>
        <p>Project Folder: <span>/home/user/projects/</span></p>
        <p>Dataset: <span>/home/apoferritin/</span></p>
      </div>
      <div class="divider"></div>
      <div class="bottom">
        <div class="item" ref="item">Download project</div>
        <div class="item_child" ref="item_child"></div>
        <el-button @mouseover.native="showPopUp()" @mouseleave.native="close()" class="btn btn_download" icon="el-icon-download" plain size="small"></el-button>
        <el-button class="btn_close" plain size="small">close</el-button>
        <el-button class="btn btn_open" plain size="small">Open</el-button>
      </div>
    </div>
  </el-card>
</template>
<script>
    export default {
        name: "ProjectCard",
        props:["image_src", "project_name"],
        data(){
          return{
            item:"",
          }
        },

        methods:{
          showPopUp(){
            this.$refs.item.style.opacity = 1;
            this.$refs.item_child.style.opacity = 1;
          },
          close(){
            this.$refs.item.style.opacity = 0;
            this.$refs.item_child.style.opacity = 0;
          }
        }
    }
</script>

<style lang="less" scoped>
  .card
  {
    height: 320px;
    border-radius: 5px;
    .title
    {
      height: 25px;
      color:white;
      font-size: 14px;
      text-align: center;
      background-color: rgb(49,138,255);
      p{
        margin:0;
        padding-top:3px;
      }
    }
    .content
    {
      margin:15px;
      height: 290px;
      .card_content{
        height: 100px;
        .card_content_detail
        {
          display: inline-block;
          height: 80px;
          font-weight: bold;
          font-size:17px;
          width:50%;
          vertical-align: top;
          padding-top: 20px;
          padding-left:5px;
        }
        .image
        {
          display: inline-block;
          width: 80px;
          height: 80px;
          border: 1px solid rgb(244,244,244);
          border-radius: 5px;

          .image_content{
            width: 73px;
            height: 23px;
            margin:30px auto;
          }
        }
      }

      .params
      {
        height: 120px;
        p{
          margin:0;
          font-size:12px;
          line-height: 1.5em;
          letter-spacing: 1px;
          color:rgb(150,150,150);
          span{
            color:rgb(200,200,200);
          }
        }
      }
      .divider{
        height: 1px;
        width:100%;
        border-top: 1px solid rgb(200,200,200);
      }
      .bottom{
        padding-top: 10px;
        .item{
          width: 120px;
          height: 23px;
          background-color: rgb(49,138,255);
          opacity: 0;
          position:absolute;
          top:240px;
          font-size:13px;
          color:white;
          text-align: center;
          -webkit-border-radius: 4px;
          -moz-border-radius: 4px;
          border-radius: 4px;
        }
        .item_child{
          content:'';
          width:2px;
          position:relative;
          top:-10px;
          left:4px;
          border-left:5px solid transparent;
          border-right:5px solid transparent;
          border-top:5px solid rgb(49,138,255);
          opacity: 0;
        }
        .btn{
          color:dodgerblue;
        }
        .btn_close, .btn_open{
          float: right;
        }
        .btn_open:hover, .btn_download:hover{
          background-color: rgb(49,138,255);
          color:white;
        }
        .btn_close:hover{
          color:rgb(49,138,255);
        }
      }
    }
  }
</style>
