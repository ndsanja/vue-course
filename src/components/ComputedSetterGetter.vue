<template>
  <h2>Full Name : {{ firstName }} {{ lastName }}</h2>
  <h2>Full Name with Computed Property : {{ fullName }}</h2>
  <button @click="changeFullName">change Full Name</button>

  <h2>
    Total - {{ items.reduce((total, curr) => (total = total + curr.price), 0) }}
  </h2>
  <h2>Total with Computed Property - {{ total }}</h2>
  <h2>Total with Method - {{ getTotal() }}</h2>
  <button @click="items.push({ id: 4, title: 'Keyboard', price: 50 })">
    add
  </button>
  <br />
  <template v-for="item in items" :key="item">
    <h2 v-if="item.price > 100">{{ item.title }} : {{ item.price }}</h2>
  </template>
  <br />
  <h2>With Computed Property</h2>
  <h2 v-for="item in expensiveItem" :key="item">
    {{ item.title }} : {{ item.price }}
  </h2>
</template>

<script>
export default {
  name: "ComputedSetterGetter",
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
  methods: {
    getTotal() {
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },
    changeFullName() {
      return (this.fullName = "Kiki Ratna");
    },
  },
  computed: {
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const name = value.split(" ");
        this.firstName = name[0];
        this.lastName = name[1];
      },
    },
    total() {
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },
    expensiveItem() {
      return this.items.filter((item) => item.price > 100);
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
