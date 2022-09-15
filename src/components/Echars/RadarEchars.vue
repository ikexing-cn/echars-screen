<script lang="ts" setup>
import { EChartsOption } from 'echarts'

const options = $ref<EChartsOption>({
  grid: {
    top: '0',
    bottom: '0',
    left: '0',
    right: '0',
  },
  radar: {
    indicator: [
      { name: 'Java Se', max: 16500 },
      { name: 'Vue 3', max: 16000 },
      { name: 'Vue 2', max: 30000 },
      { name: 'MySql', max: 38000 },
      { name: 'Redis', max: 52000 },
      { name: 'Nodejs', max: 25000 },
      { name: 'Rabbit MQ', max: 45000 },
      { name: 'Koa', max: 38000 },
      { name: 'Express', max: 16000 },
    ],
  },
  series: [
    {
      type: 'radar',
      data: [
        {
          value: [5000, 6000, 10000, 20000, 5000, 12600, 9800, 18000, 10000],
          name: '学习人数',
        },
      ],
      areaStyle: {
        opacity: 0.9,
        color: {
          x: 0,
          y: 0,
          x2: 1,
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
  tooltip: {
    show: true,
  },
})
</script>

<template>
  <echarts id="radar" :options="(options as EChartsOption)" />
</template>
