<script lang="ts" setup>
import { EChartsOption } from 'echarts'

const options = $ref<EChartsOption>({
  xAxis: {
    type: 'value',
    axisTick: {
      show: false,
    },
  },
  yAxis: {
    type: 'category',
    data: ['Java Se', 'Vue 3', 'Vue 2', 'MySql', 'Redis', 'Nodejs', 'Koa', 'Express'],
    axisTick: {
      show: false,
    },
  },
  series: [
    {
      name: '2011',
      type: 'bar',
      barWidth: 8,
      data: [100, 200, 250, 300, 350, 450, 500, 550],
      itemStyle: {
        borderRadius: 5,
        color: {
          x: 0,
          y: 0,
          x2: 1,
          y2: 0,
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
  grid: {
    left: '15%',
    top: '5%',
    bottom: '15%',
    right: '5%',
  },
  backgroundColor: '',
})
</script>

<template>
  <echarts :options="(options as EChartsOption)" />
</template>

<style lang="less" scoped>
</style>
