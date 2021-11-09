<template>
  <div class="forms">
    <form @submit="submitForm">
        <p>Your name: {{values.name}}</p>
        <p>Your country: {{values.country}}</p>
        <p>Work type: {{values.remoteWork ? 'Remote' : 'Not Remote'}}</p>
        <p>Skills are: <span v-for="s in values.skills" v-bind:key="s">{{s}}</span></p>
        <div>
            <label for='name'>Name</label>
            <input type="text" id='name' v-model="values.name"/>
            <select id="country" v-model="values.country">
                <option value="Select a country" selected>Select a country</option>
                <option value="India">India</option>
                <option value="Germany">Germany</option>
                <option value="Paris">Paris</option>
            </select>
        </div>

        <div>
            <label for='checkbox'>Choose work type: </label>
            <input type="checkbox" v-model="values.remoteWork">
        </div>

        <div>
            <label for='checkbox'>Choose skills </label>
            <div class="skills-cnt">
                <label for='checkbox'>HTML</label>
                <input type="checkbox" value="HTML" v-model="values.skills">
            </div>

            <div class="skills-cnt">
                <label for='checkbox'>Node</label>
                <input type="checkbox" value="Node" v-model="values.skills">
            </div>
            <div class="skills-cnt">
                <label for='checkbox'>JS</label>
                <input type="checkbox" value="JS" v-model="values.skills">
            </div>
            <div class="skills-cnt">
                <label for='checkbox'>React</label>
                <input type="checkbox" value="React" v-model="values.skills">
            </div>
        </div>

        <button>Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'Forms',
  data(){
      return{
          values: {
              name: '',
              country: '',
              remoteWork: false,
              skills: []
          }
      }
  },
  methods: {
      submitForm(e){
          e.preventDefault()
          console.log(this.values)
      }
  }
}
</script>

<style scoped>
.forms{
    margin-top: 20px;
    background: #279aff;
    padding: 30px;
}
input{
    display: block;
    margin: 10px auto;
    padding: 10px;
    font-size: 16px;
}
.skills-cnt{
    width: 160px;
    margin: auto;
    display: flex;
    column-gap: 10px;
    align-items: center;
    justify-content: center;
}

.skills-cnt input{
    margin: 0;
}
</style>