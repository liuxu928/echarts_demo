<template>
  <div class="content-hd">
    <ul class="hd-counter">
      <li>{{ number1 }}</li>
      <span></span>
      <li>{{ number2 }}</li>
    </ul>

    <ul class="hd-explain">
      <li>前端需求人数</li>
      <li>市场供应人数</li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from "vue";
const number1 = ref(Math.floor(Math.random().toFixed(2) * 10000));
const number2 = ref(Math.floor(Math.random().toFixed(2) * 10000));
// let number2 = ref(null);
setInterval(() => {
  number1.value += Math.floor(Math.random().toFixed(2) * 50 - 25);
  number2.value += Math.floor(Math.random().toFixed(2) * 50 - 25);
}, 1000);
</script>

<style lang="less" scoped>
.content-hd {
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  width: 41.55vw;
  height: 8.5vw;
  background: rgba(101, 132, 226, 0.1);
  padding: 1.0333vw;
  .hd-counter,
  .hd-explain {
    display: flex;
    justify-content: space-evenly;
    align-items: center;
  }
  .hd-counter {
    position: relative;
    width: 100%;
    height: 4.5vw;
    border: 1px solid rgba(25, 186, 139, 0.17);
    font-family: electronicFont;
    color: #ffff00;
    font-size: 3.2552vw;
    span {
      width: 0.1vw;
      height: 2.5vw;
      background-color: #fff;
    }
    &::before {
      content: "";
      position: absolute;
      left: 0;
      top: 0;
      width: 1.7667vw;
      height: 0.7667vw;
      border-top: 0.1067vw solid #02a6b5;
      border-left: 0.1067vw solid #02a6b5;
    }
    &::after {
      content: "";
      position: absolute;
      right: 0;
      bottom: 0;
      width: 1.7667vw;
      height: 0.7667vw;
      border-bottom: 0.1067vw solid #02a6b5;
      border-right: 0.1067vw solid #02a6b5;
    }
  }
  .hd-explain {
    font-size: 0.7667vw;
    color: #ccc;
    margin-top: 0.5vw;
    justify-content: space-around;
  }
}
</style>
