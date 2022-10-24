<template>
  <div class="content-bd" ref="centerMap">
    <div class="map1"></div>
    <div class="map2"></div>
    <div class="map3"></div>
  </div>
</template>

<script setup></script>

<style lang="less" scoped>
.content-bd {
  position: relative;
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 41.55vw;
  box-sizing: border-box;
  padding: 1.0333vw;
  overflow: hidden;
  .map1,
  .map2,
  .map3 {
    position: absolute;
  }
  .map1 {
    background: url("../assets/images/map.png") no-repeat center center;
    background-size: cover;
    z-index: 1;
    opacity: 0.3;
    width: 26vw;
    height: 26vw;
  }
  .map2 {
    background: url("../assets/images/jt.png") no-repeat center center;
    background-size: cover;
    animation: rotate2 10s linear infinite;
    z-index: 2;
    opacity: 0.5;
    width: 28.35vw;
    height: 28.35vw;
  }
  .map3 {
    width: 33vw;
    height: 33vw;
    background: url("../assets/images/lbx.png") no-repeat center center;
    background-size: cover;
    animation: rotate 20s linear infinite;
    z-index: 3;
    opacity: 1;
  }
  @keyframes rotate {
    0% {
      transform: rotate(0);
    }
    100% {
      transform: rotate(360deg);
    }
  }
  @keyframes rotate2 {
    0% {
      transform: rotate(0);
    }
    100% {
      transform: rotate(-360deg);
    }
  }
}
</style>
