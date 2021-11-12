<template>
    <div class="container">
        <h3>This is a popup component.</h3>
        <button @click="$emit('close')">Close Popup</button>
        <button @click="$emit('alert', 'Debjit')">Show name alert</button>

        <input type="number" v-model="num">
        <button @click="$emit('passNum', num)">Pass Number Greater Than 10</button>
    </div>
</template>

<script>
    export default {
        name: "ComponentEvents",
        //emits: ['close', 'alert'],
        data(){
            return{
                num: null
            }
        },
        emits: {
            passNum: (num) => {
                if(num<10) {
                    alert("Number is less than 10.")
                    return false
                }
                else return true
            }
        }
    }
</script>

<style scoped>

</style>