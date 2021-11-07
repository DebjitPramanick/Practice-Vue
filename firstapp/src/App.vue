<template>
  <div>
    <p>Hello {{name}}</p>
    <p>Age: {{age}}</p>
    <div v-text="salary"></div>
    <div v-html="el"></div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      name: "Debjit",
      age: 21,
      salary: '16K',
      el: "<strong>Developer</strong>"
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
