<template>
  <div class="top">
    <dv-border-box-7 style="width:100%;height:5.75rem">
      <div class="list">
        <div class="item">
          <p class="tit">用户数</p>
          <p class="p1">
            <countTo
              :startVal="startVal"
              :endVal="endVal1"
              :duration="duration"
            ></countTo>
            <span>人</span>
          </p>
        </div>
        <div class="item">
          <p class="tit">设备数</p>
          <p class="p1">
            <countTo
              :startVal="startVal"
              :endVal="endVal2"
              :duration="duration"
              :decimals="decimals"
            ></countTo>
            <span>台</span>
          </p>
        </div>
        <div class="item">
          <p class="tit">智能垃圾箱投递量</p>
          <p class="p1">
            <countTo
              :startVal="startVal"
              :endVal="endVal3"
              :duration="duration"
            ></countTo>
            <span>t</span>
          </p>
        </div>
        <div class="item">
          <p class="tit">小区数</p>
          <p class="p1">
            <countTo
              :startVal="startVal"
              :endVal="endVal4"
              :duration="duration"
            ></countTo>
            <span>个</span>
          </p>
        </div>
        <div class="item">
          <p class="tit">家庭组</p>
          <p class="p1">
            <countTo
              :startVal="startVal"
              :endVal="endVal5"
              :duration="duration"
            ></countTo>
            <span>户</span>
          </p>
        </div>                
      </div>
    </dv-border-box-7>
    <!-- <dv-border-box-8 style="width:100%;height:3.75rem">
      <div class="list">
        <div class="item lf">
          <p class="p1">
            用户数
            <countTo
              :startVal="startVal"
              :endVal="endVal4"
              :duration="duration"
            ></countTo>
            <span>人</span>
          </p>
          <p class="p1">
            家庭组
            <countTo
              :startVal="startVal"
              :endVal="endVal5"
              :duration="duration"
            ></countTo>
            <span>户</span>
          </p>
        </div>
        <div class="item lf">
          <p class="p1">
            智能回收站投递量
            <countTo
              :startVal="startVal"
              :endVal="endVal6"
              :duration="duration"
              :decimals="decimals"
            ></countTo>
            <span>t</span>
          </p>
          <p class="p1">
            智能垃圾箱投递量
            <countTo
              :startVal="startVal"
              :endVal="endVal7"
              :duration="duration"
              :decimals="decimals"
            ></countTo>
            <span>t</span>
          </p>
        </div>
        <div class="item lf">
          <p class="p1">
            设备数
            <countTo
              :startVal="startVal"
              :endVal="endVal8"
              :duration="duration"
            ></countTo>
            <span>台</span>
          </p>
          <p class="p1">
            小区数
            <countTo
              :startVal="startVal"
              :endVal="endVal9"
              :duration="duration"
            ></countTo>
            <span>个</span>
          </p>
        </div>
      </div>
    </dv-border-box-8> -->
  </div>
</template>

<script>
// 数字滚动
import countTo from "vue-count-to";
export default {
  data() {
    return {
      // 数字滚动
      // 需要滚动的时间
      duration: 5000,
      // 初始值
      startVal: 0,
      // 最终值
      endVal1: 30,
      endVal2: 297,
      endVal3: 4730,
      endVal4: 74576,
      endVal5: 53397,
      endVal6: 2204,
      endVal7: 18.96,
      endVal8: 448,
      endVal9: 89,
      decimals: 2
    };
  },
  components: {
    countTo
  },
  mounted() {},
  methods: {}
};
</script>

<style lang="scss" scoped>
.top {
  display: flex;
  justify-content: space-around;
  .list {
    display: flex;
    justify-content: space-between;
    padding: 0.625rem;
    box-sizing: border-box;

    .item {
      padding: 0.125rem 0;
      box-sizing: border-box;
      text-align: center;
      &.lf {
        text-align: left;
      }
      .tit {
        font-size: 1.5rem;
        color: #fff;
        line-height: 3rem;
        font-weight: bold;
      }
      .p1 {
        font-size: 1rem;
        color: #fff;
        font-weight: bold;
        span {
          font-size: 1rem;
          font-weight: bold;
        }
      }
    }
  }
}
</style>
