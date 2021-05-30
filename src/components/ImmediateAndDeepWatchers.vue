<template>
  <h2>Volume Tracker (0 - 20)</h2>
  <h3>Current Volume - {{ volume }}</h3>
  <div>
    <button @click="volume > 0 && (volume -= 2)">decrease</button>
    <button @click="volume += 2">increase</button>
  </div>
  <input type="text" name="" id="1" v-model="movie" />
  <input type="text" name="" id="2" v-model="movieInfo.title" />
  <input type="text" name="" id="3" v-model="movieInfo.actor" />

  <div>
    <button @click="movieList.push('Wonder Woman')">add movie</button>
  </div>
</template>

<script>
export default {
  name: "ImmediateAndDeepWatchers",
  data() {
    return {
      volume: 0,
      movie: "Batman",
      movieInfo: {
        title: "",
        actor: "",
      },
      movieList: ["Batman", "Superman"],
    };
  },
  methods: {},
  computed: {},
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert("jangan keras-keras yaa");
      }
      if (newValue < oldValue && newValue === 0) {
        alert("sudah yang paling kecil");
      }
    },
    movie: {
      handler(newValue) {
        console.log(`calling API with movie name ${newValue}`);
      },
      immediate: true,
    },
    movieInfo: {
      handler(newValue) {
        console.log(
          `calling API with title ${newValue.title} actor ${newValue.actor}`
        );
      },
      deep: true,
    },
    movieList: {
      handler(newValue) {
        console.log(`new movie list ${newValue}`);
      },
      deep: true,
    },
  },
};
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
