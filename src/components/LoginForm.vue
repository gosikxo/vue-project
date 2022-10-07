<script>
import { reactive } from 'vue'
import CustomInput from './CustomInput.vue'
export default {
    components: {
        CustomInput: CustomInput
    },
    setup() {
        const state = reactive({
            title: 'Login Form',
            inputs: [
                {
                    label: "Email",
                    value: '',
                    type: 'email'
                },
                {
                    label: "Password",
                    value: '',
                    type: 'password'
                }
            ],
        })

        function handleSubmit() {
            console.log(state.inputs[0].value, state.inputs[1].value)
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
        <CustomInput 
        v-for="(input, i) in state.inputs" 
        :key="i"
        v-model="input.value" 
        :label="input.label"
        :type="input.type" 
        />
        <button>Log in</button>
    </form>
</template>

<style>
input {
    margin: 10px;
    display: block;
}
</style>
  