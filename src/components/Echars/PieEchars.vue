<script lang="ts" setup>
import { EChartsOption } from 'echarts'

const options = $ref<EChartsOption>({
  grid: {
    top: '0',
    bottom: '0',
    left: '0',
    right: '0',
  },
  series: [
    {
      type: 'pie',
      roseType: 'area',
      radius: [30, '75%'],
      center: ['50%', '50%'],
      label: {
        color: 'white',
        fontSize: 14,
      },
      data: [
        {
          value: 50,
          name: '官网在线',
          itemStyle: {
            color: '#2D91F4',
          },
        },
        {
          value: 5,
          name: '离线下载',
          itemStyle: {
            color: '#4C72F0',
          },
        },
        {
          value: 20,
          name: '腾讯课堂',
          itemStyle: {
            color: '#6857ED',
          },
        },
        {
          value: 15,
          name: '网易云课堂',
          itemStyle: {
            color: '#DDDCCC',
          },
        },
      ],
      minAngle: 0,
    },
  ],
  backgroundColor: '',
})
</script>

<template>
  <echarts :options="(options as EChartsOption)" />
</template>

<style lang="less" scoped>
</style>
