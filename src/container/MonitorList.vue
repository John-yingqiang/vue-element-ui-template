<template>
  <el-row :gutter="40" style="margin:15px 0;">
    <el-col class="col" :xs="13" :sm="10" :md="8" :lg="6" :xl="1" v-for="card in cards" :key="card.index">
      <MonitorCard :title="card.title" :detail="card.detail" :class_type="card.class_type"></MonitorCard>
    </el-col>
  </el-row>
</template>

<script>
  import MonitorCard from "../components/MonitorCard"

    export default {
        name: "MonitorList",
        components: {
          MonitorCard
        },
        data(){
          return {
            cards:[
              {
                index:0,
                class_type:"icon iconfont icon-cpu_icon",
                title:"CPU",
                detail:"4/96 cores",
              },
              {
                index:1,
                class_type:"icon iconfont icon-xianqia",
                title:"GPU",
                detail:"0/16 GPU",
              },
              {
                index:2,
                class_type:"icon iconfont icon-icon_ram-memory",
                title:"Memory",
                detail:"62.9/754.7 GB",
              },
              {
                index:3,
                class_type:"icon iconfont icon-storage",
                title:"Storage",
                detail:"1 TB/10",
              },

            ]
          }
        }
    }
</script>

<style lang="less" scoped>
  @media screen and (max-width: 924px) {
    .col {
      width: 80%;
    }
  }
  @media screen and (min-width: 924px) {
    .col {
      width: 50%;
    }
  }
  @media screen and (min-width: 1200px) {
    .col {
      width: 33.33%;
    }
  }

  @media screen and (min-width: 1463px) {
    .col {
      width: 25%;
    }
  }
</style>
