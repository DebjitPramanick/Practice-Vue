<template>
    <div>
        Component1 - {{count}}
        <button @click="increment">Click to increase</button>
    </div>
</template>

<script>
    import CounterMixin from "./count"
    export default {
        name: "Component1",
        mixins: [CounterMixin]
    }
</script>

<style scoped>

</style>