<template>
  <screen-header></screen-header>
  <screen-main></screen-main>
</template>

<script setup>
import screenHeader from "./views/screenHeader";
import screenMain from "./views/screenMain";
console.log(window.screen.height);
console.log(window.screen.width);
</script>

<style lang="less"></style>
