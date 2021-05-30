<template>
  <h2>{{ name }}</h2>
  <div>
    <button @click="changeName($event), increment(1, $event)">Click</button>
  </div>
  <h2>{{ count }}</h2>
  <div>
    <button @click="count -= 1">-</button>
    <button @click="count += 1">+</button>
  </div>
  <h2 v-if="count > 0">{{ count }}</h2>
  <h2 v-else>0</h2>
  <div>
    <button @click="decrement(num)">Decrement {{ num }}</button>
    <button @click="increment(num, $event)">Increment {{ num }}</button>
  </div>
  <input type="number" name="" id="" v-model="num" />
</template>

<script>
export default {
  name: "EventHandler",
  data() {
    return {
      name: "Sanja",
      count: 0,
      num: "",
    };
  },
  methods: {
    changeName(event) {
      this.name = "Ganteng";
      console.log("event", event);
    },
    increment(num, event) {
      console.log("event", event);
      return (this.count += parseInt(this.num));
    },
    decrement(num) {
      if (this.count > 0) {
        return (this.count -= parseInt(this.num));
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
