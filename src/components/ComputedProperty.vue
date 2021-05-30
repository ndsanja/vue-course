<template>
  <h2>Full Name : {{ firstName }} {{ lastName }}</h2>
  <h2>Full Name with Computed Property : {{ fullName }}</h2>

  <h2>
    Total - {{ items.reduce((total, curr) => (total = total + curr.price), 0) }}
  </h2>
  <h2>Total with Computed Property - {{ total }}</h2>
  <button @click="items.push({ id: 4, title: 'Keyboard', price: 50 })">
    add
  </button>
</template>

<script>
export default {
  name: "ComputedProperty",
  data() {
    return {
      firstName: "Sanja",
      lastName: "Ganteng",
      items: [
        { id: 1, title: "TV", price: 100 },
        { id: 2, title: "Phone", price: 200 },
        { id: 3, title: "Laptop", price: 300 },
      ],
    };
  },
  methods: {},
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    },
    total() {
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
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
