<script lang="ts" setup>
import dayjs from 'dayjs'
</script>

<template>
  <main relative z-2>
    <h1 text="#DCFAFA 11 center" leading-24>
      大屏幕展示
    </h1>
    <p b="b-3 #23CDFD" text="#23CDFD 4.5" leading="5.5" absolute right-16 top-15>
      {{ dayjs(Date.now()).format('YYYY.MM.DD HH:MM:ss') }}
    </p>

    <div class="grid-layouts">
      <div>
        <div class="card-border">
          <e-title>每月学习时间</e-title>
          <img src="../assets/images/heng_line.png" absolute top-20 left-25>
          <bar-echars />
        </div>
        <div text-white mt-3 w-full text-center h-70>
          <e-title>学习最多课程</e-title>
          <radar-echars />
        </div>
      </div>
      <div text-center relative>
        <div class="low-card left">
          <span text-white>今日购买课程</span>
          <span text="red 4xl" mt-2>114</span>
        </div>
        <div class="low-card right">
          <span text-white>今日新增人数</span>
          <span text="#33DBFB 4xl" mt-2>514</span>
        </div>
        <map-echars />
        <e-title>全国地域分布</e-title>
      </div>
      <div>
        <div class="card-border">
          <e-title>上线课程学习</e-title>
          <img src="../assets/images/heng_line.png" absolute top-20 left-25>
          <horizontal-echarts />
        </div>
        <div text-white mt-3 w-full text-center h-70>
          <e-title>学习方式</e-title>
          <pie-echars />
        </div>
      </div>
    </div>
  </main>
</template>

<style lang="less" scoped>
.grid-layouts {
  gap: 100px;
  display: grid;
  padding: 5px 40px;
  grid-template-columns: 420px 1fr 420px;
}

.card-border {
  height: 333px;
  display: flex;
  padding-top: 40px;
  flex-direction: column;
  justify-content: center;
  position: relative;
  background: url('~/assets/images/chart1_bg.png') no-repeat;
}

.low-card {
  z-index: 100;
  width: 195px;
  height: 95px;
  padding-top: 12px;
  position: absolute;
  text-align: center;
  display: flex;
  flex-direction: column;
  background: url('~/assets/images/card_bg.png') no-repeat;

  &.left {
    left: 0;
    bottom: 0;
  }

  &.right {
    right: 0;
    bottom: 0;
  }
}
</style>
