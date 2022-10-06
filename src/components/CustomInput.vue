<script>
export default {
    props: {
        label: String
    },
    setup() {

    }
}
</script>
    
<template>
    <label>
        {{ label }}
        <input type="text" v-model="inputValue">
    </label>

</template>
    
<style>

</style>
      