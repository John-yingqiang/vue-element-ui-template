<template>
  <div>
    <el-row ref="myrow">
      <el-col class="pie" :span="24">
        <PieChart></PieChart>
      </el-col>
    </el-row>
    <el-row>
      <el-col class="line" :span="24">
        <LineChart :width="autoWidth"></LineChart>
      </el-col>
    </el-row>
  </div>
</template>

<script>
    import PieChart from "./PieChart";
    import LineChart from "./Line";

    export default {
        name: "ChartList",
        data(){
          return {
            my_row:null,
          }
        },
        components:{
          PieChart,
          LineChart,
        },
        mounted(){
          this.my_row = this.$refs.myrow;
        },
        computed:{
          autoWidth(){
            if(this.my_row){
              return this.my_row.style.width;
            }
          }
        }
    }
</script>

<style scoped>

</style>
