<template>
    <div class="container">
        <h3>Mixin Components</h3>
        <component-1 />
        <component-2 />
    </div>
</template>

<script>
    import Component1 from './Component1.vue'
    import Component2 from './Component2.vue'
    import CounterMixin from "./count"
    export default {
        components: { Component1, Component2 },
        name: "Main",
        mixins: [CounterMixin]
    }
</script>

<style scoped>

</style>