<script setup>
  let greeting = 'hello'
  const isVisible = true
  const isVisible2 = false
</script>

<template>
  <div id="app" v-cloak>
    <h1> {{greeting}} </h1>
    <input v-model="greeting"/>
    <div class="box" v-if="isVisible"></div>
    <div class="box2" v-else-if="isVisible2"></div>
    <div class="box3" v-else></div>
  </div>
</template>

<style>
  .box {
    background-color: red;
    width: 40px;
    height: 40px;
  }
  .box2 {
    background-color: blue;
    width: 40px;
    height: 40px;
  }
  .box3 {
    background-color: pink;
    width: 40px;
    height: 40px;
  }
  [v-cloak] {
    display: none
  }
</style>
