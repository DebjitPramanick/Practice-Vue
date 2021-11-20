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

    <Greet name="Debjit" age=20 likes=20 nickname="Sujan" />

    <ProvideInject />
    <h3 v-if="number!==null">The number is: {{number}}</h3>
    <ComponentEvents v-show="showComponent" 
    @close="closePopup"
    @alert="showName"
    @passNum="setNum"/>

    <InputModel v-model="name"/>

    <Card content="Card content 1">
      It is slot for first card
      <template v-slot:footer>
        <h3>Footer</h3>
      </template>
    </Card>

    <Card content="Card content 2">
      <input type="text">
      <template v-slot:footer>
        <h3>Footer</h3>
      </template>
    </Card>

    <Card content="Card content 1">
      <button>Sample</button>
      <template v-slot:footer>
        <h3>Footer</h3>
      </template>
    </Card>
    <NameList>
      <template v-slot:default="slotProps">
        {{slotProps.first}} {{slotProps.last}}
      </template>
    </NameList>

    <TabContainer />

    <HTTPComponent />

    <TemplateRef />

    <Main />

    <DataRef />

    <MethodsRef />

  </div>
</template>

<script>

import Methods from './Methods.vue'
import Forms from './Forms.vue'
import GetterSetter from './GetterSetter.vue'
import Watchers from './Watchers.vue'
import Greet from './components/Greet.vue'
import ProvideInject from './components/ProvideInject.vue'
import ComponentEvents from "./components/ComponentEvents.vue"
import InputModel from "./components/InputModel.vue"
import Card from "./slots/Card.vue"
import NameList from "./slots/NameList.vue"
import TabContainer from "./components/dynamic_components/TabContainer.vue"
import HTTPComponent from "./HTTP/HTTPComponents.vue"
import TemplateRef from "./components/TemplateRef.vue"
import Main from "./mixins/Main.vue"
import DataRef from './composition_api/DataRef.vue'
import MethodsRef from './composition_api/MethodsRef.vue'

export default {
  name: 'App',
  components: {
    Methods,
    Forms,
    GetterSetter,
    Watchers,
    Greet,
    ProvideInject,
    ComponentEvents,
    InputModel,
    Card,
    NameList,
    TabContainer,
    HTTPComponent,
    TemplateRef,
    Main,
    DataRef,
    MethodsRef
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
      ],
      showComponent: true,
      number: null,
    }
  },
  methods: {
    closePopup(){
      this.showComponent=false
    },
    showName(name){
      alert(name)
    },
    setNum(num){
      this.number = num
    }
  },
  provide(){
    return {
      name: this.name
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

.container {
  background: #ffc65d;
  padding: 30px;
  max-width: 1400px;
  margin: 30px auto;
  font-size: 18px;
}
.container.flex {
  background: #ffc65d;
  padding: 30px;
  max-width: 1400px;
  margin: 30px auto;
  display: flex;
  align-items: center;
  justify-content: center;
  column-gap: 16px;
  font-size: 18px;
}
.container h3{
  display: block;
  margin: 0 0 16px 0;
}
p {
  display: block;
  margin: 4px 0;
}
.container .icons {
  cursor: pointer;
  font-size: 20px;
  width: 30px;
  height: 30px;
  text-align: center;
}
</style>
