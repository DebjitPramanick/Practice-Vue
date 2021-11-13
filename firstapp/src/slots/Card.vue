<template>
    <div class="container">
        <h3>Card with Slots</h3>
        <p>{{content}}</p>
        <slot></slot>
    </div>
</template>

<script>
    export default {
        name: "Card",
        props: ['content']
    }
</script>

<style scoped>

</style>