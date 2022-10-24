<template>
  <div class="header">
    <h1>可视化展板-Echarts</h1>
    <div class="date">当前时间:2022年10月20日-17时33分25秒</div>
  </div>
</template>

<script setup></script>

<style lang="less" scoped>
.header {
  position: relative;
  height: 5.3333vw;
  background: url("../assets/images/head_bg.png") no-repeat top center;
  background-size: 100% 100%;
  h1 {
    text-align: center;
    color: #fff;
    font-size: 1.7333vw;
    line-height: 5.3333vw;
  }
  .date {
    position: absolute;
    top: 1.6667vw;
    right: 1.6667vw;
    color: #fff;
    font-size: 1.0667vw;
  }
}
</style>
