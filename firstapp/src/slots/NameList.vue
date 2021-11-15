<template>
    <div class="container">
        <h3>Slot Props</h3>
        <h4 v-for="name in names" :key="name.first">
            <slot :first="name.first" :last="name.last"></slot>
        </h4>
    </div>
</template>

<script>
    export default {
        name: "NameList",
        data(){
            return{
                names: [
                    {first: "Debjit", last: "Pramanick"},
                    {first: "Rohan", last: "Biswas"},
                    {first: "David", last: "Johanson"},
                    {first: "Lara", last: "Page"},
                ]
            }
        }
    }
</script>

<style scoped>

</style>