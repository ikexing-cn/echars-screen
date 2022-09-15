<script lang="ts" setup>
import axios from 'axios'
import * as echarts from 'echarts'
import type { EChartsOption, EChartsType } from 'echarts'

const { options } = defineProps<{
  options: EChartsOption
}>()
const chinaJson = (await axios.get('https://geo.datav.aliyun.com/areas_v3/bound/100000_full.json')).data
echarts.registerMap('chinaMap', chinaJson)

let echart = $ref<EChartsType>()
const echarsContainer = $ref<HTMLDivElement>()

watch(() => options, (options) => {
  echart && echart.setOption(options)
}, { deep: true })

onMounted(() => {
  echart = echarts.init(echarsContainer, 'dark')
  echart.setOption(options)
})
</script>

<template>
  <div ref="echarsContainer" class="w-full h-full" />
</template>
