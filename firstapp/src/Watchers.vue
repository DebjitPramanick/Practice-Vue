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

