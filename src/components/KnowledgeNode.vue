<template>
  <v-chart class="chart" :option="option" autoresize />
</template>

<script setup>
import VChart from 'vue-echarts'
import { ref } from 'vue'

//paste to here
import { use } from 'echarts/core'
import { GraphChart } from 'echarts/charts'
import { TitleComponent, TooltipComponent } from 'echarts/components'
import { SVGRenderer } from 'echarts/renderers'

use([TitleComponent, TooltipComponent, GraphChart, SVGRenderer])

const option = ref({
  title: {
    text: 'Basic Graph',
  },
  tooltip: {},
  animationDurationUpdate: 1500,
  animationEasingUpdate: 'quinticInOut',
  series: [
    {
      type: 'graph',
      layout: 'none',
      symbolSize: 50,
      roam: true,
      label: {
        show: true,
      },
      edgeSymbol: ['circle', 'arrow'],
      edgeSymbolSize: [4, 10],
      edgeLabel: {
        fontSize: 20,
      },
      symbol: 'roundRect',
      data: [
        {
          name: '',
          x: 300,
          y: 100,
          symbol: 'none',
        },
        {
          name: 'Front-end',
          x: 300,
          y: 300,
        },
        {
          name: 'Internet',
          x: 300,
          y: 500,
        },
      ],
      links: [
        {
          source: '',
          target: 'Front-end',
          label: {
            show: false,
          },
          lineStyle: {
            type: 'dashed',
            curveness: 0,
          },
        },
        {
          source: 'Front-end',
          target: 'Internet',
          label: {
            show: false,
          },
          lineStyle: {
            curveness: 0,
          },
        },
      ],
      lineStyle: {
        opacity: 0.9,
        width: 2,
        curveness: 0,
      },
    },
  ],
})
</script>

<style scoped>
.chart {
  height: 100vh;
}
</style>
