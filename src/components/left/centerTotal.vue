<template>
  <div id="centerLeft1">
    <div class="">
      <div class="d-flex pt-2 pl-2">
        <span style="color:#5cd9e8">
          <icon name="chart-bar"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl mx-2" style="font-size:16px;padding:0 10px">设备总台数</span>
          <dv-decoration-3 style="width:8rem;height:0.6rem; position:relative;top:0.3rem;" />
        </div>
      </div>
      <div class="d-flex all-box">
      <div class=" jc-center">
        <CenterLeft1Chart />
      </div>
      <!-- 4个主要的数据 -->
      <div class="bottom-data">
          <div class="item-box" v-for="(item,index) in numberData" :key="index">
              <div class="nums">
                  <dv-digital-flop :config="item.number" style="width:100%;height:30px;" />
              </div>
              <span style="width:50px;text-align: center;">{{item.text}}</span>
          </div>
      </div>
       </div>
    </div>
  </div>
</template>

<script>
import CenterLeft1Chart from "@/components/echart/centerLeft/centerLeft1Chart";
export default {
  data() {
    return {
      numberData: [
        {
          number: {
            number: [300],
            content: "{nt}"
          },
          text: "正常"
        },
        {
          number: {
            number: [180],
            content: "{nt}"
          },
          text: "清运"
        },
        {
          number: {
            number: [80],
            content: "{nt}"
          },
          text: "满溢"
        },
        {
          number: {
            number: [10],
            content: "{nt}"
          },
          text: "故障"
        }           
      ]
    };
  },
  components: {
    CenterLeft1Chart
  },
  mounted() {
    this.changeTiming();
  },
  methods: {
    changeTiming() {
      setInterval(() => {
        // this.changeNumber();
      }, 3000);
    },
    changeNumber() {
      this.numberData.forEach((item, index) => {
        item.number.number[0] += ++index;
        item.number = { ...item.number };
      });
    }
  }
};
</script>

<style lang="scss">
#centerLeft1 {
  padding: 0.2rem;
  height: 15.625rem;
  min-width: 18.75rem;
  border-radius: .625rem;
  .bg-color-black {
    // height: 24rem;
    border-radius: 0.625rem;
  }
  .text {
    color: #c3cbde;
  }
  .chart-box {
    margin-top: 1.2rem;
    width: 12rem;
    height: 12rem;
    .active-ring-name {
      padding-top: 0.625rem;
    }
  }
.all-box{
          display: flex;
      justify-content: space-around;
}
  .bottom-data {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-around;
      padding: .625rem;
      box-sizing: border-box;
    .item-box {
    display: flex;
    justify-content: space-around;
    .nums{
        font-size: 2rem;
    }
      color: #d3d6dd;
      // 金币
      .coin {
        position: absolute;
        left: 0.6rem;
        top: 1rem;
        font-size: 0.875rem;
        color: #ffc107;
      }
      .colorYellow {
        color: yellowgreen;
      }
    }
  }
}
</style>