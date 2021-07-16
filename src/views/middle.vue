<template>
  <div id="center">
    <dv-border-box-13 style="width:100%;height:980px;">
      <div class="mapBox">

      </div>
    </dv-border-box-13>
  
  </div>
</template>

<script>
import lineChart from "@/components/left/lineChart";

export default {
  data () {
    return {

    };
  },
  components: {
lineChart
  }
};
</script>

<style lang="scss" scoped>
#center {
  display: flex;
  justify-content: space-around;
  .mapBox{
    display: flex;
    justify-content: space-between;
    padding: 0.625rem;
    box-sizing: border-box;
  }

}
</style>