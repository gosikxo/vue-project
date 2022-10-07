<script>
import { reactive, computed } from 'vue'

export default {
    props: {
        label: String,
        modelValue: String,
        type: String
    },
    emits: ['update:modelValue'],
    setup(props, ctx) {
        const state = reactive({ inputValue: ''})
        const inputValue = computed({
        get() {
            return props.modelValue
        },
        set(value) {
            ctx.emit('update:modelValue', value)
        }
})

        return {
            state, inputValue
        }
    }
}
</script>
    
<template>
    <label>
        {{ label }}
        <input :type="type" v-model="inputValue">
    </label>

</template>
    
<style>

</style>
      