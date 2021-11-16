<template>
    <div class="container">
        <h3>Template Ref</h3>
        <input ref="inputRef"/>
    </div>
</template>

<script>
    export default {
        name: "TemplateRef",
        mounted(){
            this.$refs.inputRef.focus()
        }
    }
</script>

<style scoped>

</style>