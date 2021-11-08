<template>
  <div class="hello">
    <h2>{{add(2)}}</h2>
    <h2>{{multiply()}}</h2>
    <div>
        <h1>{{name}}</h1>
        <button v-on:click="name = 'Batman'">Change Name</button>
    </div>
    <div>
        <h1>{{count}}</h1>
        <button v-on:click="count += 1">Increment</button>
        <button v-on:click="count -= 1">Decrement</button>
        <button v-on:click="increment">Increment Func</button>
        <button v-on:click="decrement">Decrement Func</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Methods',
  props: {
    msg: String
  },
  data(){
      return{
          base: 2,
          name: "Debjit",
          count: 0
      }
  },
  methods: {
      add(a){
          return 1+2+a
      },
      multiply(){
          return 10 *this.base
      },
      increment(){
          this.count += 2
      },
      decrement(){
          this.count -= 2
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>