<script lang="ts" setup>
import { EChartsOption } from 'echarts'

const options = $ref<EChartsOption>({
  xAxis: {
    type: 'category',
    data: ['老王', '老李', '老张', '老赵', '老孙', '老周', '老吴', '小王', '小李', '小张'],
    axisTick: {
      show: false,
    },
  },
  yAxis: {
    max: 100,
    min: 0,
    splitNumber: 10,
    name: '单位：小时',
    nameTextStyle: {
      color: 'white',
      fontSize: '14px',
    },
  },
  series: [
    {
      type: 'bar',
      data: [75, 78, 89, 90, 77, 86, 76, 78, 82, 95],
      barWidth: 6,
      itemStyle: {
        borderRadius: 5,
        color: {
          x: 0,
          y: 0,
          x2: 0,
          y2: 1,
          type: 'pattern',
          colorStops: [
            { offset: 0, color: '#2D91F4' },
            { offset: 0.5, color: '#4C72F0' },
            { offset: 1, color: '#6857ED' },
          ],
          global: false,
        },
      },
    },
  ],
  backgroundColor: '',
  grid: {
    top: '30px',
    bottom: '40px',
    left: '50px',
    right: '25px',
  },
})
</script>

<template>
  <echarts :options="(options as EChartsOption)" />
</template>
