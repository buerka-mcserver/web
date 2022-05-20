<script lang="ts" setup>
import * as echarts from 'echarts/core'
import { GridComponent, GridComponentOption } from 'echarts/components'
import { LineChart, LineSeriesOption } from 'echarts/charts'
import { UniversalTransition } from 'echarts/features'
import { CanvasRenderer } from 'echarts/renderers'
import { onMounted } from 'vue'

onMounted(() => {

  echarts.use([GridComponent, LineChart, CanvasRenderer, UniversalTransition])

  type EChartsOption = echarts.ComposeOption<
    GridComponentOption | LineSeriesOption
  >;

  let chartDom: HTMLElement = document.querySelector('.status-echarts')!
  let myChart = echarts.init(chartDom)
  let option: EChartsOption

  // 临时用假数据
  option = {
    xAxis: {
      type: 'category',
      boundaryGap: false,
      data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
    },
    yAxis: {
      type: 'value'
    },
    series: [
      {
        data: [820, 932, 901, 934, 1290, 1330, 1320],
        type: 'line',
        areaStyle: {}
      }
    ]
  }

  option && myChart.setOption(option)

})

</script>

<template>
  <div class="status">
    <h1>实时状态</h1>
    <div class="status-echarts"></div>
  </div>
</template>

<style lang="less" scoped>
.status {
  padding-top: 40px;
}
.status-echarts {
  width: 100%;
  height: 200px;
}
</style>