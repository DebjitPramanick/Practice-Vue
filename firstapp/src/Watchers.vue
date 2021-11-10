<template>
  <div>
    <div class="container">
      <button @click="volume -= 2">-</button>
      <p>Volumen Level: {{ volume }}</p>
      <button @click="volume += 2">+</button>
    </div>
    <input type="text" v-model="movie" />
    <input type="text" v-model="movieInfo.title" />
    <input type="text" v-model="movieInfo.actor" />
  </div>
</template>

<script>
export default {
  name: "Watchers",
  data() {
    return {
      volume: 0,
      movie: 'Batman',
      movieInfo: {
          title: '',
          actor: ''
      }
    };
  },
  methods: {},
  computed: {},
  watch: {
    // Watcher
    volume(newVal, oldVal) {
      if (newVal > oldVal && newVal === 16) alert("Volume is too high.");
    },
    movie:{
        handler(newVal){
            console.log("Calling API with movie name = "+newVal)
        },
        imediate: true // For watching simple variable
    },
    movieInfo: {
        handler(newVal){
            console.log("Calling API with movie name = "+newVal.title)
            console.log("Calling API with movie actor = "+newVal.actor)
        },
        deep: true // For watching object and arrays
    }
  },
};
</script>

<style scoped>
.container {
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
.container p {
  margin: 0;
}
.container button {
  cursor: pointer;
  font-size: 20px;
  width: 30px;
  height: 30px;
  text-align: center;
}
</style>
