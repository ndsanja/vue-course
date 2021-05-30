<template>
  <h2>Add method: {{ add(3, 5) }}</h2>
  <h2>Add method: {{ add(6, 10) }}</h2>
  <h2>Multiply method: {{ multiply(dataNum) }}</h2>
</template>

<script>
export default {
  name: "Methods",
  data() {
    return {
      baseNumber: 9,
      dataNum: 120,
    };
  },
  methods: {
    add(a, b) {
      return a + b;
    },
    multiply(num) {
      return this.baseNumber * num;
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
