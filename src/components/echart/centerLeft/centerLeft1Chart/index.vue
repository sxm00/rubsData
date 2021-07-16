<template>
  <div>
    <Chart :cdata="cdata" />
  </div>
</template>

<script>
import Chart from './chart.vue';
export default {
  data () {
    return {
      cdata: {
        xData: ["正常", "清运", "满溢", "故障"],
        seriesData: [
          { value: 300, name: "正常" },
          { value: 180, name: "清运" },
          { value: 80, name: "满溢" },
          { value: 10, name: "故障" },
        ]
      }
    }
  },
  components: {
    Chart,
  },
  mounted () {
  },
  methods: {
  }
}
</script>

<style lang="scss" scoped>
</style>