<template>
  <el-row :gutter="40" style="margin:15px 0">
    <el-col class="col" :xs="13" :sm="10" :md="8" :lg="6" :xl="1" v-for="card in project_cards" :key="card.index">
      <ProjectCard :image_src="card.image_src" :project_name="card.project_name" ></ProjectCard>
    </el-col>
  </el-row>
</template>

<script>
  import ProjectCard from "../components/ProjectCard"

    export default {
        name: "ProjectsList",
        components:{
          ProjectCard,
        },
      data(){
          return {
            project_cards:[
              {
                index:0,
                image_src: require("../static/images/relion.png"),
                project_name: "去铁铁蛋白分析"
              },
              {
                index:1,
                image_src: require("../static/images/cistem.png"),
                project_name:"Si圈上的选择性GaN"
              },
              {
                index:2,
                image_src: require("../static/images/lammps.png"),
                project_name: "ZrO2上的疯牛病毒分析"
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
