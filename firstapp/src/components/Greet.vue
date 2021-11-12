<template>
    <div>
        <p>{{name}}-{{age}}</p>
        <h3>{{likes}} - {{nickname}}</h3>
    </div>
</template>

<script>
    export default {
        name: 'Greet',
        // props: ['name', 'age'],
        props: {
            likes: Number,
            nickname: String
        }
    }
</script>

<style scoped>

</style>