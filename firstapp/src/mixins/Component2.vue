<template>
    <div>
        Component2 - {{count}}
        <button @click="increment">Click to increase</button>
    </div>
</template>

<script>
    import CounterMixin from "./count"
    export default {
        name: "Component2",
        mixins: [CounterMixin]
    }
</script>

<style scoped>

</style>