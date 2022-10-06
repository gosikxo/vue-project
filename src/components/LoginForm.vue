<script>
import { reactive } from 'vue'
export default {
    setup() {
        const state = reactive({ title: 'Login Form', email: "", password: "" })

        function handleSubmit() {
            console.log(state.password)
        }

        return {
            state, handleSubmit
        }
    }
}
</script>

<template>
    <form @submit.prevent="handleSubmit">
        <h1>{{ state.title }}</h1>
        <input type="email" v-model="state.email">
        <input type="password" v-model="state.password">
        <button>Log in</button>
    </form>
</template>

<style>
input {
    margin: 10px;
    display: block;
}
</style>
  