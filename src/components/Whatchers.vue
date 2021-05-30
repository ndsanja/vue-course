<template>
  <h2>Volume Tracker (0 - 20)</h2>
  <h3>Current Volume - {{ volume }}</h3>
  <div>
    <button @click="volume > 0 && (volume -= 2)">decrease</button>
    <button @click="volume += 2">increase</button>
  </div>
</template>

<script>
export default {
  name: "Whatchers",
  data() {
    return {
      volume: 0,
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
