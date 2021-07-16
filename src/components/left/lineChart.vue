<template>
  <div id="centerRight1">
    <div class="d-flex pt-2 pl-2">
      <span style="color:#5cd9e8">
        <icon name="chart-line"></icon>
      </span>
      <div class="d-flex">
        <span class="fs-xl  mx-2" style="font-size:16px;padding:0 10px"
          >投递总量TOP5小区</span
        >
      </div>
    </div>
    <div class="chartBox">
      <div class="echarts" ref="echarts"></div>
    </div>
  </div>
</template>

<script>
import echarts from "echarts";
export default {
  name: "safe",
  data() {
    return {
      chartInstance: null
    };
  },
  mounted() {
    this.initChart();
    window.addEventListener("resize", this.screenAdapter);
    // 在页面加载完成的时候, 主动进行屏幕的适配
    this.screenAdapter();
  },
  destroyed() {
    // 在组件销毁的时候, 需要将监听器取消掉
    window.removeEventListener("resize", this.screenAdapter);
  },
  methods: {
    // 初始化echartInstance对象
    initChart() {
      this.chartInstance = echarts.init(this.$refs.echarts);
      // 对图表初始化配置的控制
      var initOption = {
        grid: {
            top:"-1%",
          left: "3%",
          right: "4%",
          bottom: "3%",
          containLabel: true
        },
        xAxis: {
          type: "value",
          splitLine: { show: false },
          show: false
        },
        yAxis: {
          type: "category",
          axisLabel: {
            formatter: "{value}",
            textStyle: {
              color: "#fff"
            }
          },
          axisLine: {
            lineStyle: {
              color: "#fff",
              width: 1 //这里是为了突出显示加上的
            }
          },
          axisTick: {
            //y轴刻度线
            show: false
          },
          axisLine: {
            //y轴
            show: false
          },
          data: ["新新家园", "小康人家", "阳光名都", "天一苑", "文昌花园"],
          splitLine: { show: false }
        },
        tooltip: {
          trigger: "axis",
          axisPointer: {
            type: "shadow"
          }
        },
        series: [
          {
            name: "投递量",
            type: "line",
            label: {
              show: true,
              position: "right",
              textStyle: {
                color: "white"
              }
            },
            stack: "总量",
            itemStyle: {
              color: {
                type: "linear",
                x: 0,
                y: 0,
                x2: 0,
                y2: 1,
                colorStops: [
                  {
                    offset: 0,
                    color: "#1CD8D2" // 0% 处的颜色
                  },
                  {
                    offset: 1,
                    color: "#ffffff" // 100% 处的颜色
                  }
                ],
                global: false // 缺省为 false
              }
            },
            lineStyle: {
              color: {
                type: "linear",
                x: 0,
                y: 0,
                x2: 1,
                y2: 1,
                colorStops: [
                  {
                    offset: 0,
                    color: "#ffffff" // 0% 处的颜色
                  },
                  {
                    offset: 0.5,
                    color: "#5865FF" // 0% 处的颜色
                  },
                  {
                    offset: 1,
                    color: "#ffffff" // 100% 处的颜色
                  }
                ],
                global: false // 缺省为 false
              }
            },
            areaStyle: {
              color: {
                type: "linear",
                x: 0,
                y: 0,
                x2: 0,
                y2: 1,
                colorStops: [
                  {
                    offset: 0,
                    color: "blue" // 0% 处的颜色
                  },
                  {
                    offset: 1,
                    color: "#027aee" // 100% 处的颜色
                  }
                ],
                global: false // 缺省为 false
              }
            },
            emphasis: {
              focus: "series"
            },
            data: [18.2, 18.8, 20.3, 21, 22]
          }
        ]
      };

      this.chartInstance.setOption(initOption);
    },

    // 当浏览器的大小发生变化的时候, 会调用的方法, 来完成屏幕的适配
    screenAdapter() {
      const titleFontSize = (this.$refs.echarts.offsetWidth / 100) * 3.6;
      // 和分辨率大小相关的配置项
      const adapterOption = {
        title: {
          textStyle: {
            fontSize: titleFontSize
          }
        },
        tooltip: {
          axisPointer: {
            lineStyle: {
              width: titleFontSize
            }
          }
        },
        series: [
          {
            barWidth: titleFontSize,
            itemStyle: {
              barBorderRadius: [0, titleFontSize / 2, titleFontSize / 2, 0]
            }
          }
        ]
      };
      this.chartInstance.setOption(adapterOption);
      // 手动的调用图表对象的resize 才能产生效果
      this.chartInstance.resize();
    }
  }
};
</script>

<style scoped lang="scss">
#centerRight1 {
    width: 100%;
     padding: 0.2rem;
  height: 15.625rem;
  min-width: 6.75rem;
  border-radius:1rem;

}
.chartBox {
  width: 28.125rem;
  height: 15.625rem;
  padding: 0 0 20px 0;
  box-sizing: border-box;
  .echarts {
    width: 100%;
    height: 100%;
  }
}
</style>
