<template>
    <div class="container">
        <h3>Composition API</h3>
        <p>Composition val - {{cFirstName}}</p>
    </div>
</template>

<script>
    import {ref} from 'vue'
    export default {
        name: "DataRef",
        setup(){
            const cFirstName = ref('Clark') // Reactive reference to the value (Reactive and Mutable)

            return {
                cFirstName
            }
        }
    }
</script>

<style scoped>

</style>