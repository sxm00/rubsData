<template>
  <div id="index">
    <!-- <dv-full-screen-container class="bg"> -->
      <dv-loading v-if="loading">Loading...</dv-loading>
      <div v-else class="host-body">
        <!-- <div class="d-flex jc-center jc-top">
            <div class="title">
              <span class="title-text">瓜子壳垃圾分类数据监管平台</span>
              <dv-decoration-6
                class="title-bototm"
                :reverse="true"
                :color="['#50e3c2', '#67a1e5']"
                style="width:17rem;height:1rem;"
              />
            </div>
            <div>
               <span class="text">{{dateYear}} {{dateWeek}} {{dateDay}}</span>
            </div>
        </div> -->



        <div class="body-box">
          <!-- 第三行数据 -->
          <div class="content-box">
           
            <div class="left">
              <!-- 头部 -->
              <div>
              <centerTop></centerTop>    
              </div>

              <div>
                <centerUp></centerUp>   
              </div>
              <div>
                <center></center>
              </div>
              <div>
                <bottomLeft></bottomLeft>
              </div>
              <div>
                <bottomLeft1></bottomLeft1>
              </div>
            </div>
            <!-- 中间 -->
            <div class="middle">
              <div class="d-flex jc-center jc-top" style="width:100%;height:5.55rem;">
                  <div class="title">
                    <span class="title-text">瓜子壳垃圾分类数据监管平台</span>
                    <dv-decoration-6
                      class="title-bototm"
                      :reverse="true"
                      :color="['#50e3c2', '#67a1e5']"
                      style="width:17rem;height:1rem;"
                    />
                  </div>
              </div>   
              <div>
                <middle></middle>
              </div>         
            </div>
            <!-- 右侧 -->
            <div class="right">
              <div class="d-flex jc-center" style="width:100%;height:5.55rem">
                  <div>
                    <span class="timeD">{{dateYear}} {{dateWeek}} {{dateDay}}</span>
                  </div>
              </div>   
              <div>
                <rightTop></rightTop>
              </div> 
              <div>
               <bottomRight></bottomRight>
              </div>    
            </div>
          </div>
        </div>
      </div>
    <!-- </dv-full-screen-container> -->
  </div>
</template>

<script>
import { formatTime } from '@/utils/index.js'

// 左侧
import center from "./center";
import centerTop from "./centerTop";
import centerUp from "./centerUp";
import bottomLeft from "./bottomLeft";
import bottomLeft1 from "./bottomLeft1";
import middle from './middle.vue';
import rightTop from './rightTop.vue';
import bottomRight from './bottomRight.vue';
export default {
  data () {
    return {
      loading: true,

      // 倒计时
      dateDay: null,
      dateYear: null,
      dateWeek: null,
      weekday: ["周日", "周一", "周二", "周三", "周四", "周五", "周六"],
    };
  },
  components: {
center,
centerTop,
centerUp,
bottomLeft,
bottomLeft1,
    middle,
    rightTop,
    bottomRight
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