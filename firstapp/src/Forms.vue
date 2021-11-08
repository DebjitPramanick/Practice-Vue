<template>
  <div class="forms">
    <form>
        <p>Your name: {{values.name}}</p>
        <p>Your country: {{values.country}}</p>
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
              country: ''
          }
      }
  },
  methods: {
      
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
</style>