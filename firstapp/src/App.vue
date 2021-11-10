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

    <!-- Conditional rendering -->

    <h2 v-if="num==0">The number is 0.</h2>
    <h2 v-else>The number is not 0. It is {{num}}.</h2>

    <h1 v-show="showEl">Using V-Show</h1>


    <!-- List rendering -->

    <h2 v-for="name in names" :key="name">{{name}}</h2>

    <h2 v-for="t in things" :key="t.type">
      {{t.type}} - {{t.name}}
    </h2>

    <h2 v-for="s in shops" :key="s.name">
      {{s.name}}: 
      <span v-for="i in s.items" :key="i" style="margin-right: 10px">{{i}}</span>
    </h2>

    <template v-for="name in names" :key="name">
      <h2 v-if="name === 'Debjit'">{{name}}</h2>
    </template>

    <Methods />
    <Forms />
    <GetterSetter />
    <Watchers />

    <Greet name="Debjit" age=20 />

  </div>
</template>

<script>

import Methods from './Methods.vue'
import Forms from './Forms.vue'
import GetterSetter from './GetterSetter.vue'
import Watchers from './Watchers.vue'
import Greet from './Greet.vue'

export default {
  name: 'App',
  components: {
    Methods,
    Forms,
    GetterSetter,
    Watchers,
    Greet
  },
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
      num: 4,
      showEl: true,
      names: ['Debjit', 'Rakesh', 'Richard'],
      things: [
        {type: 'Food', name: 'Pasta'},
        {type: 'Toy', name: 'Doll'},
        {type: 'Electronics', name: 'Mobile'},
      ],
      shops: [
        {
          name: 'Grocerry',
          items: ['Rice', 'Oil']
        },
        {
          name: 'Food',
          items: ['Burger', 'Pizza']
        },
      ]
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

input{
  padding: 8px;
  font-size: 16px;
  display: block;
  margin: 8px auto;
}
</style>
