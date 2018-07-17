<template>
  <el-row :gutter="40" style="margin:15px 0;">
    <el-col :span="24">
        <el-card class="box_card">
          <div slot="header" class="header">
            <span>Job</span>
            <div class="divider"></div>
          </div>
          <div class="operation">
            <span>Status</span>
            <div class="btn">
              <el-button class="el-button running" type="primary" plain>Running</el-button>
              <el-button class="el-button stopped" type="primary" plain>Stopped</el-button>
              <el-button class="el-button completed" type="primary" plain>Completed</el-button>
            </div>
            <span>Queue</span>
            <div class="select">
              <el-select v-model="value" placeholder="请选择">
                <el-option
                  key="1"
                  label="label"
                  value="value">
                </el-option>
              </el-select>
            </div>
            <div class="search">
              <el-input class="input" v-model="input" placeholder="Search"></el-input>
              <el-button class="button" icon="el-icon-search"></el-button>
            </div>
            <el-row>
              <el-col class="col" :xs="24" :sm="24" :md="12" :lg="12" :xl="12" >
                <JobList></JobList>
              </el-col>
              <el-col class="col" :xs="24" :sm="24" :md="12" :lg="12" :xl="12">
                <ChartList></ChartList>
              </el-col>
            </el-row>

          </div>
        </el-card>
    </el-col>
  </el-row>

</template>

<script>
    import JobList from "../components/JobList"
    import ChartList from "../components/ChartList"

    export default {
        name: "JobContainer",
        components:{
          JobList,
          ChartList,
        },
        data(){
          return{
            input:"",
            value:'',
          }
        }
    }
</script>

<style lang="less" scoped>
.operation{
  span{
    padding-right: 10px;
    font-size: 18px;
  }
  .btn{
    display: inline-block;
    .running{
      -webkit-border-radius: 8px 0 0 8px;
      -moz-border-radius: 8px 0 0 8px;
      border-radius: 8px 0 0 8px;
    }
    .stopped{
      margin-left: -4px;
      -webkit-border-radius: 0;
      -moz-border-radius: 0;
      border-radius: 0;
    }
    .completed{
      margin-left: -4px;
      -webkit-border-radius: 0 8px 8px 0;
      -moz-border-radius: 0 8px 8px 0;
      border-radius: 0 8px 8px 0;
    }
  }
  .select{
    display:inline-block;
  }
  .search{
    float:right;
    display: inline-block;
    .input{
      width:70%;
    }
    .button{
      margin:-3px;
    }
  }
}

@media screen and (max-width: 587px) {
  .btn {
    width: 80%;
    margin-bottom: 20px;
    .el-button{
      padding-left:2px;
      padding-right:2px;
    }
  }
  .operation span{
    display:block;
  }
  .select{
    width:80%;
    margin-bottom: 20px;
  }
  .search{
    width:100%;
    margin-bottom: 10px;
    .button{
      padding-left:15px;
      padding-right:15px;
    }
  }
}

@media screen and (min-width: 587px) {
  .btn {
    width: 80%;
    margin-bottom: 20px;
    .el-button{
      padding-left:2px;
      padding-right:2px;
    }
  }
  .select{
    width:31%;
  }
  .search{
    width:39%;
    .button{
      padding-left:8px;
      padding-right:8px;
    }
  }
}
@media screen and (min-width: 924px) {
  .btn {
    width: 90%;
    margin-bottom: 20px;
  }
}
@media screen and (min-width: 1200px) {
  .btn{
    width:30%;
    padding-right: 0;
    .el-button{
      padding-left:5px;
      padding-right:5px;
    }
  }
  .select{
    width:15%;
  }
}
@media screen and (min-width: 1463px) {
  .btn {
    width: 30%;
    padding-right: 60px;
    .el-button{
      padding-left:15px;
      padding-right:15px;
    }
  }
  .select{
    width:15%;
  }
  .search{
    width:30%;
  }
}

</style>
