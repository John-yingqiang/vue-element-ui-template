<template>
  <div>
    <el-row>
      <el-col class="job" :span="24">
        <JobTitle></JobTitle>
      </el-col>
    </el-row>
    <el-row>
      <el-col :span="24" v-for="card in cards" :key="card.index">
        <Job :name="card.name" :status="card.status" :queue="card.queue" ></Job>
      </el-col>
    </el-row>
  </div>
</template>

<script>
    import Job from "./Job"
    import JobTitle from "./JobTitle"

    export default {
        name: "JobList",
        components:{
          Job,
          JobTitle,
        },
      data(){
          return {
            cards:[{
              index:0,
              name:"去铁铁蛋白分析",
              status:"Running",
              queue:"compute"
            },
              {
                index:1,
                name:"去铁铁蛋白分析",
                status:"Running",
                queue:"compute"
              },
              {
                index:2,
                name:"去铁铁蛋白分析",
                status:"Running",
                queue:"compute"
              },
              {
                index:3,
                name:"去铁铁蛋白分析",
                status:"Running",
                queue:"compute"
              },
              {
                index:4,
                name:"去铁铁蛋白分析",
                status:"Running",
                queue:"compute"
              },
              {
                index:5,
                name:"去铁铁蛋白分析",
                status:"Running",
                queue:"compute"
              },
              {
                index:6,
                name:"去铁铁蛋白分析",
                status:"Running",
                queue:"compute"
              }
            ],
          }
      }
    }
</script>

<style scoped>
  .job{
    height: 50px;
  }
  .job:nth-child(even){
    background-color: rgb(251, 251, 251);
  }
</style>
