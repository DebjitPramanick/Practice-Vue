<template>
  <div class="hello">
    <h2>{{add(2)}}</h2>
    <h2>{{multiply()}}</h2>
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
          base: 2
      }
  },
  methods: {
      add(a){
          return 1+2+a
      },
      multiply(){
          return 10 *this.base
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