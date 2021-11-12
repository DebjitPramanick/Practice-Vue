<template>
    <div>
        <div class="container">
            <h3>ProvideInject</h3>
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