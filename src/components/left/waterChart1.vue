<template>
  <div class="chartBox">
     <div  class="echarts" ref="echarts1"></div>
    <div class="text">准确率 <span>89%</span></div>    
  </div>
</template>

<script>
import echarts from "echarts";
import 'echarts-liquidfill/src/liquidFill.js'
export default {
  name: "waterChart",
  data() {
    return {

    };
  },
  mounted() {
    this.echartsMit();
  },

  methods: {
// 绘制指标图
      echartsMit() {
        var myChart = echarts.init(this.$refs.echarts1);
        myChart.setOption({
        series: [{
            type: 'liquidFill',
            data: [0.89,0.5],
        color: ['#017cee', '#017cee'],
        itemStyle: {
            opacity: 0.6
        },
        emphasis: {
            itemStyle: {
                opacity: 0.9
            }
        },
        backgroundStyle: {
            borderWidth: 3,
            borderColor: '#017cee',
            color: '#03153a'
        },
         outline: {
            show: false
        },
        label: {
            fontSize: 28,
            color: '#017cee'
        }        
        }]
        });
 
      },


  }
};
</script>

<style scoped lang="scss">
.chartBox {
  width: 100%;
  height: 100%;
  .echarts {
    width: 225px;
    height: 200px;
    margin: -20px 0 0 0;
  }
  .text{
      margin: -30px 0 0 10px;
      font-size: .875rem;
      text-align: center;
}
}
</style>
