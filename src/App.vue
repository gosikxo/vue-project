<script>
import { reactive } from 'vue'
import LoginForm from './components/LoginForm.vue'

export default {
  components: {
    LoginForm: LoginForm
  },
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
    <LoginForm />
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
