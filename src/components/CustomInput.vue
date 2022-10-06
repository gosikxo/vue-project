<script>
import { reactive, computed } from 'vue'

export default {
    props: {
        label: String
    },
    setup() {
        const state = reactive({ inputValue: ''})

        return {
            state
        }
    }
}
</script>
    
<template>
    <label>
        {{ label }}
        <input type="text" v-model="state.inputValue">
    </label>

</template>
    
<style>

</style>
      