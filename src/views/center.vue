<template>
  <div id="center">
    <dv-border-box-13 style="width:480px;height:250px;">
      <div class="list">
        <!-- <tableScroll></tableScroll>    -->
      </div>
    </dv-border-box-13>
    <dv-border-box-13 style="width:480px;height:250px;">
      <div class="list">
       
      </div>
    </dv-border-box-13>    
  </div>
</template>

<script>
import tableScroll from "@/components/left/tableScroll";

export default {
  data () {
    return {

    };
  },
  components: {
tableScroll
  }
};
</script>

<style lang="scss" scoped>
#center {
  display: flex;
  justify-content: space-around;
  .list{
    display: flex;
    justify-content: space-between;
    padding: 0.625rem;
    box-sizing: border-box;
  }

}
</style>