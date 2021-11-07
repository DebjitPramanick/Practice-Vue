<template>
  <div>
    <p>Hello {{name}}</p>
    <p>Age: {{age}}</p>
    <div v-text="salary"></div>

    <div v-html="el"></div>
    
    <p v-bind:id="headingId">Heading</p>
    <button v-bind:disabled="isDisabled">Bind</button>

    <h2 v-bind:style="{
      color: highlightColor,
      'font-size': 50+'px',
      backgroundColor: 'blue'
    }"
    >Inline style</h2>

    <h2 v-bind:style="{
      color: highlightColor,
      'font-size': 50+'px',
      backgroundColor: 'blue'
    }"
    >Style Object</h2>


    <div v-bind:style="[fontStyles, colorStyles]">Success Style</div>

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
      el: "<strong>Developer</strong>",
      headingId: "heading",
      isDisabled: true,
      highlightColor: 'orange',
      styleObject: {
        color: 'orange',
        fontSize: '50px',
        backgroundColor: 'blue'
      },
      fontStyles: {
        fontSize: '30px',
        fontWeight: 600,
        fontStyle: 'italic'
      },
      colorStyles: {
        color: 'white',
        backgroundColor: 'red'
      },
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
