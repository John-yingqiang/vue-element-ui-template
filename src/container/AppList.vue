<template>
  <el-row :gutter="40" style="margin:15px 0;">
    <el-col class="col" :xs="13" :sm="10" :md="8" :lg="6" :xl="1" v-for="card in app_cards" :key="card.index">
      <AppCard :image_src="card.image_src" :details="card.details" ></AppCard>
    </el-col>
  </el-row>
</template>

<script>
    import AppCard from "../components/AppCard"

    export default {
        name: "AppList",
        components:{
          AppCard,
        },
        data(){
          return {
            app_cards:[
              {
                index:0,
                image_src:require("../static/images/cistem.png"),
                details:"A description for Cry-EM to show its title",
              },
              {
                index:1,
                image_src:require("../static/images/gromacs.png"),
                details:"A description for Cry-EM to show its title",
              },
              {
                index:2,
                image_src:require("../static/images/relion.png"),
                details:"A description for Cry-EM to show its title",
              },
              {
                index:3,
                image_src:require("../static/images/lammps.png"),
                details:"A description for Cry-EM to show its title",
              }],
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
