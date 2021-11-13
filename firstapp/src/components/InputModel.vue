<template>
    <div class="container">
        <h3>Input Model</h3>
        <input type="text" :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)">
    </div>
</template>

<script>
    export default {
       name: "InputModel",
       props: {
           modelValue: String
       }
    }
</script>

<style scoped>

</style>