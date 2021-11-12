<template>
    <div class="container">
        <h3>This is a popup component.</h3>
        <button @click="$emit('close')">Close Popup</button>
        <button @click="$emit('alert', 'Debjit')">Show name alert</button>
    </div>
</template>

<script>
    export default {
        name: "ComponentEvents",
        emits: ['close', 'alert']
    }
</script>

<style scoped>

</style>