<script setup lang="ts">
import * as echarts from 'echarts'
import Home from '~/pages/index.vue'
import chinaMap from '~/json/china.json'

echarts.registerMap('chinaMap', chinaMap as any)
</script>

<template>
  <Suspense>
    <Home />
  </Suspense>
</template>
