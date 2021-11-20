<template>
    <div class="container">
        <h3>Composition API For Methods</h3>
        <p>{{firstname}} - {{lastname}}</p>
        <button @click="changeName">Change Name</button>
    </div>
</template>

<script>
    import {reactive, toRefs} from 'vue'
    export default {
        name: "MethodsRef",
        setup(){
            const state = reactive({
                firstname: "Debjit",
                lastname: "Pramanick"
            })

            const changeName = () => {
                state.firstname = "Bruce"
                state.lastname = "Wayne"
            }
            
            return {
                ...toRefs(state),
                changeName
            }
        }
    }
</script>

<style scoped>

</style>