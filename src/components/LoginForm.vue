<script>
import { reactive } from 'vue'
import CustomInput from './CustomInput.vue'
export default {
    components: {
        CustomInput: CustomInput
  },
    setup() {
        const state = reactive({ title: 'Login Form', email: "", password: "", emailLabel: "Email", passwordLabel: "Password" })

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
        <CustomInput type="email" :label="state.emailLabel" />
        <CustomInput type="password" :label="state.passwordLabel" />
        <button>Log in</button>
    </form>
</template>

<style>
input {
    margin: 10px;
    display: block;
}
</style>
  