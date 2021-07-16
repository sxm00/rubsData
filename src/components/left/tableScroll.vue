<template>
  <div id="centerRight1">
    <div class="">
      <div class="d-flex pt-2 pl-2">
        <span style="color:#5cd9e8">
          <icon name="chart-line"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl  mx-2" style="font-size:16px;padding:0 10px">实时投递用户</span>
        </div>
      </div>
      <div class="d-flex jc-center body-box">
        <dv-scroll-board :config="config" style="width:100%;height:12rem;" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      config: {
        header: ["昵称", "手机号码", "小区","品类","重量(kg)","时间"],
        data: [
          ["庄三1", "151****4366","江苏安全谷...","纸品","2", "14:39:33"],
          ["庄三2", "151****4366","江苏安全谷...","纸品","2", "14:39:33"],
          ["庄三3", "151****4366","江苏安全谷...","纸品","2", "14:39:33"],
          ["庄三4", "151****4366","江苏安全谷...","纸品","2", "14:39:33"],
          ["庄三5", "151****4366","江苏安全谷...","纸品","2", "14:39:33"],
          ["庄三6", "151****4366","江苏安全谷...","纸品","2", "14:39:33"],
          ["庄三7", "151****4366","江苏安全谷...","纸品","2", "14:39:33"],
        ],
        rowNum: 5, //表格行数
        headerHeight: 35,
        headerBGC: "#0a2ddd", //表头
        oddRowBGC: "#0a32dd", //奇数行
        evenRowBGC: "#09198e", //偶数行
        // index: true,
        columnWidth: [80,100,90,50,80,80,],
        align: ["center","center","center","center","center","center"]
      }
    };
  },
  components: {},
  mounted() {},
  methods: {}
};
</script>

<style lang="scss" scoped>
#centerRight1 {
    width: 100%;
     padding: 0.2rem;
  height: 15.625rem;
  min-width: 6.75rem;
  border-radius:1rem;
  .bg-color-black {
    border-radius: 1rem;
  }
  .text {
    color: #c3cbde;
  }
  .body-box {
    border-radius: 1rem;
    overflow: hidden;
  }
}
</style>