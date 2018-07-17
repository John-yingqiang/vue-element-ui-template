<template>
  <div class="charts_line" ref="charts_line">
    <div class="mychart" ref="mychart_line" :style="{width:width,height:'300px'}"></div>
  </div>
</template>

<script>
  let echarts = require('echarts/lib/echarts')
  require('echarts/lib/chart/line')
  require('echarts/lib/component/tooltip')
  require('echarts/lib/component/legend')
  require("echarts/lib/component/title")
  require("echarts/lib/component/grid")
  require("echarts/lib/component/toolbox")

  export default {
    name: "LineChart",
    props:['width'],
    data(){
      return {
        myChart:null,
        chart_line:null,
        charBox:null
      }
    },
    mounted(){
      this.chart_line = this.$refs.mychart_line;
      this.myChart = echarts.init(this.chart_line,"light");
      this.drawLine();
    },
    updated() {
      this.drawLine();
    },
    methods:{
      drawLine() {
        if(this.myChart)
        {
          let option = {
            title: {
              text: 'Job status'
            },
            tooltip: {
              trigger: 'axis'
            },
            legend: {
              data: ["running", "closed"]
            },
            grid: {
              left: '3%',
              right: '4%',
              bottom: '3%',
              containLabel: true
            },
            toolbox: {
              feature: {
                saveAsImage: {}
              }
            },
            xAxis: {
              type: 'category',
              boundaryGap: false,
              data: ['周一', '周二', '周三', '周四', '周五', '周六', '周日']
            },
            yAxis: {
              type: 'value'
            },
            series: [
              {
                color: ["rgb(112,162,255)"],
                name: 'running',
                type: 'line',
                stack: '总量',
                data: [10, 50, 30, 24, 80, 30, 50]
              },
              {
                color: "rgb(106,204,2)",
                name: 'closed',
                type: 'line',
                stack: '总量',
                data: [40, 92, 80, 20, 12, 35, 78]
              }
            ]
          };
          this.myChart.setOption(option)
        }
      }
    }
  }
</script>

<style lang="less" scoped>
  .charts_line{
    border:solid 1px rgb(200,200,200);
    margin-left:30px;
    margin-top:20px;

  }

</style>
