<template>
  <div class="panel">
    <slot></slot>
    <div class="panel-footer"></div>
  </div>
</template>

<script setup></script>

<style lang="less" scoped>
.panel {
  position: relative;
  width: 26.6667vw;
  height: 16.4vw;
  border: 0.0333vw solid rgba(25, 186, 139, 0.17);
  margin-bottom: 0.5333vw;
  background: url("../assets/images/line(1).png") no-repeat;
  background-size: cover;
  &::before {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    width: 0.7667vw;
    height: 0.7667vw;
    border-top: 0.1067vw solid #02a6b5;
    border-left: 0.1067vw solid #02a6b5;
  }
  &::after {
    content: "";
    position: absolute;
    right: 0;
    top: 0;
    width: 0.7667vw;
    height: 0.7667vw;
    border-top: 0.1067vw solid #02a6b5;
    border-right: 0.1067vw solid #02a6b5;
  }
  .panel-footer {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    &::before {
      content: "";
      position: absolute;
      left: 0;
      bottom: 0;
      width: 0.7667vw;
      height: 0.7667vw;
      border-bottom: 0.1067vw solid #02a6b5;
      border-left: 0.1067vw solid #02a6b5;
    }
    &::after {
      content: "";
      position: absolute;
      right: 0;
      bottom: 0;
      width: 0.7667vw;
      height: 0.7667vw;
      border-bottom: 0.1067vw solid #02a6b5;
      border-right: 0.1067vw solid #02a6b5;
    }
  }
}
</style>
