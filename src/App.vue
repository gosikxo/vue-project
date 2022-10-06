<script>
import { reactive } from 'vue'

export default {
  setup() {
    const state = reactive({ isVisible: true, greeting: "Hello!" })

    function toggleBox() {
      console.log(state.isVisible)
      state.isVisible = !state.isVisible
    }

    function greet() {
      console.log(state.greeting)
    }

    return {
      state, toggleBox, greet
    }
  }
}
</script>

<template>
  <div id="app" v-cloak>
    {{state.greeting}}
    <input @keyup.enter="greet" v-model="state.greeting" />
    <hr />
    <button @click="toggleBox">Toggle box</button>
    <div v-if="state.isVisible" class="box"></div>
  </div>
</template>

<style>
.box {
  background-color: pink;
  width: 40px;
  height: 40px;
}

[v-cloak] {
  display: none
}
</style>
