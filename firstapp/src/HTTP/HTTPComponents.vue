<template>
    <div class="container">
        <h3>HTTP Component</h3>
        <button @click="getPosts()">Fetch Posts</button>
        <p v-for="p in posts.slice(0, 5)" :key="p.id">{{p.title}}</p>
        <h3>GET Req using lifecycle method</h3>
        <div class="flex">
            <p v-for="p in lcPosts.slice(0, 5)" :key="p.id">{{p.title}}</p>
        </div>
    </div>
</template>

<script>
    import axios from "axios"
    export default {
        name: "HTTPComponent",
        created(){
            axios.get("https://jsonplaceholder.typicode.com/posts")
                .then(res => this.lcPosts = res.data)
        },
        data(){
            return{
                posts: [],
                lcPosts: []
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