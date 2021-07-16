<template>
  <div id="bottomRight">
    <dv-border-box-13 style="width:100%;height:260px;">
      <div class="list">
        <!-- <lineChart></lineChart> -->
      </div>
    </dv-border-box-13>
    <dv-border-box-13 style="width:100%;height:260px;">
      <div class="list">
       
      </div>
    </dv-border-box-13>  
  </div>
</template>

<script>

export default {
  data() {
    return {};
  },
  components: {
 
  },
  mounted() {},
  methods: {}
};
</script>

<style lang="scss">
#bottomRight {
  //  display: flex;
  // justify-content: space-around;
  .list{
    display: flex;
    justify-content: space-between;
    padding: 0.625rem;
    box-sizing: border-box;
  }
}
</style>