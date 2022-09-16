<script lang="ts" setup>
import * as echarts from 'echarts'
import type { EChartsOption, EChartsType } from 'echarts'
import chinaMap from '~/json/china.json'

const { options } = defineProps<{
  options: EChartsOption
}>()
echarts.registerMap('chinaMap', chinaMap as any)

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
