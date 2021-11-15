<template>
    <div class="container">
        <h3>HTTP Component</h3>
        <button @click="getPosts()">Fetch Posts</button>
        <p v-for="p in posts.slice(0, 5)" :key="p.id">{{p.title}}</p>
    </div>
</template>

<script>
    import axios from "axios"
    export default {
        name: "HTTPComponent",
        data(){
            return{
                posts: []
            }
        },
        methods: {
            getPosts() {
                axios.get("https://jsonplaceholder.typicode.com/posts")
                .then(res => this.posts = res.data)
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>