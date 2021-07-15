<template>
  <div class="up">
    <dv-border-box-13 style="width:480px;height:200px;">
      <div class="list">
        <div class="item">
          <piedChart></piedChart>
        </div>
        <div class="item">
          <!-- <piedChart1></piedChart1> -->
        </div>        
      </div>
    </dv-border-box-13>
    <dv-border-box-13 style="width:480px;height:200px;"> 
      <div class="list">
        <div class="item">
          <!-- <waterChart></waterChart> -->
        </div>
        <div class="item">
          <!-- <waterChart1></waterChart1> -->
        </div>         
      </div>
    </dv-border-box-13>    
  </div>
</template>

<script>
// 3d饼图
import piedChart from "@/components/left/piedChart";
import piedChart1 from "@/components/left/piedChart1";
import waterChart from "@/components/left/waterChart";
import waterChart1 from "@/components/left/waterChart1";
export default {
  name: "centerLeft2",
  data() {
    return {};
  },
  components: {
 piedChart,
 piedChart1,
 waterChart,
 waterChart1


  },
  mounted() {},
  methods: {}
};
</script>

<style lang="scss" scoped>
.up{
 display: flex;
  justify-content: space-around;
  .list {
    display: flex;
    justify-content: space-between;
    padding: 0.625rem;
    box-sizing: border-box;
  }
}
</style>