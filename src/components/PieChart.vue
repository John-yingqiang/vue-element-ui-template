<template>
    <div class="charts" ref="charts">
      <div ref="mychart" :style="{width: '100%', height: '200px'}"></div>
    </div>
</template>

<script>
    let echarts = require('echarts/lib/echarts')
    require('echarts/lib/chart/pie')
    require('echarts/lib/component/tooltip')
    require('echarts/lib/component/legend')
    require("echarts/lib/component/title")

    export default {
        name: "PieChart",
        data(){
          return {
            myChart:null,
          }
        },
        mounted(){
          let chartBox = this.$refs.charts;
          let mychart = this.$refs.mychart;

          mychart.style.width = chartBox.style.width + 'px';
          mychart.style.height = chartBox.style.height + 'px';

          this.myChart = echarts.init(mychart,"light");
          this.drawPie();
        },
        updated(){
          if(this.myChart)
          {
              this.drawPie();
          }},
        methods:{
          drawPie(){
            let option = {
              title:{
                text:"Job Status",
                x:"left"
              },
              tooltip: {
                trigger: 'item',
                formatter: "{a} <br/>{b}: {c} ({d}%)"
              },
              legend: {
                orient: 'vertical',
                right:30,
                top:30,
                bottom:20,
                data:["running","closed"]
              },
              series: [
                {
                  name:'status',
                  type:'pie',
                  radius: ['50%', '70%'],
                  avoidLabelOverlap: false,
                  color:["rgb(112,162,255)","rgb(106,204,2)"],
                  label: {
                    normal: {
                      show: false,
                      position: 'center'
                    },
                    emphasis: {
                      show: true,
                      textStyle: {
                        fontSize: '20',
                        fontWeight: 'bold'
                      }
                    }
                  },
                  labelLine: {
                    normal: {
                      show: false
                    }
                  },
                  data:[
                    {value:20, name:'running'},
                    {value:80, name:'closed'},
                  ]
                }
              ]
            };
            this.myChart.setOption(option)
          }
        }
    }
</script>

<style lang="less" scoped>
.charts{
  border:solid 1px rgb(200,200,200);
  margin-left:30px;
}
</style>
