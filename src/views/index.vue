<template>
  <div id="index">
    <dv-full-screen-container class="bg">
      <dv-loading v-if="loading">Loading...</dv-loading>
      <div v-else class="host-body">
        <div class="d-flex jc-center">
          <dv-decoration-10 style="width:33.3%;height:.0625rem;" />
          <div class="d-flex jc-center">
            <dv-decoration-8 :color="['#568aea', '#0023b4']" style="width:2.5rem;height:.625rem;" />
            <div class="title">
              <span class="title-text">瓜子壳垃圾分类数据监管平台</span>
              <dv-decoration-6
                class="title-bototm"
                :reverse="true"
                :color="['#50e3c2', '#67a1e5']"
                style="width:3.125rem;height:.1rem;"
              />
            </div>
            <dv-decoration-8
              :reverse="true"
              :color="['#568aea', '#0023b4']"
              style="width:2.5rem;height:.625rem;"
            />
          </div>
          <dv-decoration-10 style="width:33.3%;height:.0625rem; transform: rotateY(180deg);" />
        </div>

        <!-- 第二行 -->
        <div class="d-flex jc-between px-2">
          <div class="d-flex" style="width: 40%;opacity:1;">
            <div
              class="react-right ml-4"
              style="width: 6.25rem; text-align: left;background-color: #0023b4;"
            >
              <span class="react-before"></span>
              <span class="text"></span>
            </div>
            <div class="react-right ml-3" style="background-color: #0023b4;">
              <span class="text colorBlue"></span>
            </div>
          </div>
          <div style="width: 40%;" class="d-flex">
            <div class="react-left bg-color-blue mr-3" style="opacity:1;">
              <span class="text fw-b"></span>
            </div>
            <div
              class="react-left mr-4"
              style="width: 6.25rem; background-color: #0023b4; text-align: right;"
            >
              <span class="react-after"></span>
              <span class="text">{{dateYear}} {{dateWeek}} {{dateDay}}</span>
            </div>
          </div>
        </div>

        <div class="body-box">
          <!-- 第三行数据 -->
          <div class="content-box">
            <div class="left">
              <div class="top">
              <dv-border-box-8>             
                <div class="list">
                  <div class="item">
                    <p class="tit">小哥入驻人数</p>
                    <p class="p1">
                      888<span>人</span>
                      <!-- <countTo :startVal='startVal' :endVal='endVal1' :duration='duration' :decimals='decimals'></countTo> -->
                    </p>                  
                  </div>
                  <div class="item">
                    <p class="tit">上门回收总量</p>
                    <p class="p1">
                      888<span>人</span>
                      <!-- <countTo :startVal='startVal' :endVal='endVal1' :duration='duration' :decimals='decimals'></countTo> -->
                    </p>                  
                  </div>
                  <div class="item">
                    <p class="tit">上门回收订单量</p>
                    <p class="p1">
                      30<span>人</span>
                      <!-- <countTo :startVal='startVal' :endVal='endVal1' :duration='duration' :decimals='decimals'></countTo> -->
                    </p>                  
                  </div>                                    
                </div>
                </dv-border-box-8>   
                <dv-border-box-8>
                <div class="list">
                  <div class="item">
                    <p class="tit">用户数666</p>
                    <p class="p1">
                      家庭人员<span>80人</span>
                      <!-- <countTo :startVal='startVal' :endVal='endVal1' :duration='duration' :decimals='decimals'></countTo> -->
                    </p>                  
                  </div>
                  <div class="item">
                    <p class="tit">用户数666</p>
                    <p class="p1">
                      家庭人员<span>80人</span>
                      <!-- <countTo :startVal='startVal' :endVal='endVal1' :duration='duration' :decimals='decimals'></countTo> -->
                    </p>                  
                  </div>
                  <div class="item">
                    <p class="tit">用户数666</p>
                    <p class="p1">
                      家庭人员<span>80人</span>
                      <!-- <countTo :startVal='startVal' :endVal='endVal1' :duration='duration' :decimals='decimals'></countTo> -->
                    </p>                  
                  </div>                                    
                </div>
                </dv-border-box-8>
              </div>                
              <div class="up">
                
              </div>

            </div>
            <!-- 中间 -->
            <div class="middle">
              
            </div>
            <!-- 中间 -->
            <div class="right">
              
            </div>
          </div>
        </div>
      </div>
    </dv-full-screen-container>
  </div>
</template>

<script>
import { formatTime } from '@/utils/index.js'
import demoChart from "@/components/demoChart";
export default {
  data () {
    return {
      loading: true,
      dateDay: null,
      dateYear: null,
      dateWeek: null,
      weekday: ["周日", "周一", "周二", "周三", "周四", "周五", "周六"],
    };
  },
  components: {
demoChart
  },
  mounted () {
    this.timeFn();
    this.cancelLoading();
  },
  methods: {
    timeFn () {
      setInterval(() => {
        this.dateDay = formatTime(new Date(), 'HH: mm: ss');
        this.dateYear = formatTime(new Date(), 'yyyy-MM-dd');
        this.dateWeek = this.weekday[new Date().getDay()];
      }, 1000)
    },
    cancelLoading () {
      setTimeout(() => {
        this.loading = false;
      }, 500);
    }
  }
};
</script>

<style lang="scss">
@import '../assets/scss/index.scss';
</style>