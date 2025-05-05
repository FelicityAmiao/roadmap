<template>
  <v-chart class="chart" :option="option" autoresize />
</template>

<script setup>
import VChart from 'vue-echarts'
import { ref } from 'vue'

import { use } from 'echarts/core'
import { LineChart } from 'echarts/charts'
import { GridComponent } from 'echarts/components'
import { SVGRenderer } from 'echarts/renderers'

use([GridComponent, LineChart, SVGRenderer])

const option = ref({
  xAxis: {
    type: 'category',
    data: ['A', 'B', 'C'],
  },
  yAxis: {
    type: 'value',
  },
  series: [
    {
      data: [120, 200, 150],
      type: 'line',
    },
  ],
})
</script>

<style scoped>
.chart {
  height: 100vh;
}
</style>
