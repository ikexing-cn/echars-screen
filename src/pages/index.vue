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
      <div class="card-border">
        <span text="#23CDFD 7 center" font-bold leading="12.5">每月学习时间</span>
        <img src="assets/images/heng_line.png" absolute top-20 left-25>
        <bar-echars />
      </div>
      <div />
      <div class="card-border" />
    </div>
  </main>
</template>

<style lang="less" scoped>
.grid-layouts {
  gap: 40px;
  display: grid;
  padding: 5px 40px;
  grid-template-columns: 420px 1fr 420px;
}

.card-border {
  width: 420px;
  height: 330px;
  display: flex;
  padding-top: 40px;
  flex-direction: column;
  justify-content: center;
  position: relative;
  background-image: url('assets/images/chart1_bg.png');
}
</style>
