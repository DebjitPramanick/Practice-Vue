<template>
    <div>
        <div class="container">
            <h1>Component</h1>
            <p>Username is: {{name}}</p>
        </div>
        
    </div>
</template>

<script>
    export default {
        name: 'ProvideInject',
        data() {

        },
        inject: ['name']
    }
</script>

<style scoped>

</style>