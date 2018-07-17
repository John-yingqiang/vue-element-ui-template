<template>
    <el-main class="main">
      <MainTile :vm="vm"></MainTile>
      <Header :title_src="AppTitle"></Header>
      <AppList></AppList>
      <Header :title_src="ProjectTitle"></Header>
      <ProjectList></ProjectList>
      <Header :title_src="MonitorTitle"></Header>
      <MonitorList></MonitorList>
      <JobContainer></JobContainer>
    </el-main>
</template>

<script>
    import MainTile from "../components/MainTile"
    import Header from "../components/TitleHeader"
    import AppList from "./AppList"
    import ProjectList from "./ProjectsList"
    import MonitorList from "./MonitorList"
    import JobContainer from "./JobContainer"
    import AppTile from "../static/images/App.png"
    import ProjectTitle from "../static/images/my_projects.png"
    import MonitorTitle from "../static/images/Monitor.png"

    export default {
        name: "MainFrame",
        components:{
          JobContainer,
          MonitorList,
          Header,
          AppList,
          ProjectList,
          MainTile,
        },
        props:["vm"],
        data(){
          return {
            AppTitle: AppTile,
            ProjectTitle: ProjectTitle,
            MonitorTitle:MonitorTitle,
          }
        }
    }
</script>

<style scoped>
  .main{
    background-color: rgb(248,248,248);
    padding:0;
  }
</style>
