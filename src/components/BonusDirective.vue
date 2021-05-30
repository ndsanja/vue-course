<template>
  <h2>{{ name }}</h2>
  <h2 v-once>{{ name }}</h2>
  <button @click="changeName">change name</button>
  <h2 v-pre>{{ name }}</h2>
</template>

<script>
export default {
  name: "BonusDirective",
  data() {
    return {
      name: "Sanja",
    };
  },
  methods: {
    changeName() {
      this.name = "Ganteng";
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
