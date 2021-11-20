<template>
    <div class="container">
        <h3>Composition API</h3>
        <p>Composition val - {{cFirstName}}</p>
        <p>Reactive vals - {{state.name}}, {{state.age}}, {{state.occupation}}</p>
    </div>
</template>

<script>
    import {ref, reactive} from 'vue'
    export default {
        name: "DataRef",
        setup(){
            const cFirstName = ref('Clark') // Reactive reference to the value (Reactive and Mutable)

            const state = reactive({ // Same as ref but takes everything at once
                name: 'Debjit',
                age: 21,
                occupation: 'Developer'
            })

            return {
                cFirstName,
                state
            }
        }
    }
</script>

<style scoped>

</style>