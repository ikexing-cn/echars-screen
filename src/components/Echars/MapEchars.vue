import { EChartsOption } from 'echarts';
<script lang="ts" setup>
import { EChartsOption } from 'echarts'

const options = $ref<EChartsOption>({
  geo: {
    type: 'map',
    map: 'chinaMap', // chinaMap需要和registerMap中的第一个参数保持一致
    roam: true, // 设置允许缩放以及拖动的效果
    emphasis: {
      label: {
        show: true,
        color: '#ddd',
        fontSize: 14,
      },
    },
    label: {
      show: true,
      color: 'white',
      fontSize: 10,
    },
    zoom: 1.6, // 设置初始化的缩放比例
    center: [105, 36], // 设置地图中心点的坐标
    itemStyle: {
      color: 'white',
      areaColor: {
        x: 0,
        y: 0,
        x2: 0,
        y2: 1,
        type: 'pattern',
        colorStops: [
          { offset: 0, color: '#6857ED' },
          { offset: 0.5, color: '#2D91F4' },
          { offset: 1, color: '#4C72F0' },
        ],
        global: false,
      },
    },
  },
  backgroundColor: '',
})
</script>

<template>
  <echarts :options="(options as EChartsOption)" />
</template>
