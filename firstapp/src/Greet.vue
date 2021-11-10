<template>
    <div>
        <p>{{name}}-{{age}}</p>
    </div>
</template>

<script>
    export default {
        name: 'Greet',
        props: ['name', 'age']
    }
</script>

<style scoped>

</style>