<template>
  <h2 v-if="num === 0">The number is zero</h2>
  <h2 v-else-if="num > 0">Number is positive</h2>
  <h2 v-else-if="num < 0">Number is negative</h2>
  <h2 v-else>Not number</h2>

  <template v-if="display">
    <h1>Nila</h1>
    <h1>Dwi</h1>
    <h1>Sanja</h1>
  </template>

  <h2 v-show="showElement">using v-show</h2>
</template>

<script>
export default {
  name: "ConditionalRender",
  data() {
    return {
      num: 21,
      display: true,
      showElement: true,
    };
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
