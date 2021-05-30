<template>
  <h2 v-for="(name, index) in names" :key="name">
    {{ index + 1 }} - {{ name }}
  </h2>
  <h2 v-for="(name, index) in fullName" :key="name.firstName">
    {{ index + 1 }} - {{ name.firstName }}
    {{ name.lastName }}
  </h2>

  <div v-for="(name, index) in kegiatan" :key="name.firstName">
    <h2>{{ index + 1 }} - {{ name.firstName }} {{ name.lastName }}</h2>
    <h3 v-for="hobbie in name.hobbies" :key="hobbie">
      {{ hobbie }}
    </h3>
  </div>

  <template v-for="(value, key, index) in info" :key="value">
    <h1>{{ index + 1 }} {{ key }}: {{ value }}</h1>
    <hr />
  </template>
  <template v-for="name in names" :key="name">
    <h2 v-if="name === 'Sanja'">{{ name }}</h2>
  </template>
</template>

<script>
export default {
  name: "ListRendering",
  data() {
    return {
      names: ["nila", "dwi", "Sanja"],
      fullName: [
        { firstName: "Nila", lastName: "Sanja" },
        { firstName: "Kiki", lastName: "Ratna" },
        { firstName: "Ajeng", lastName: "Tsani" },
      ],
      kegiatan: [
        {
          firstName: "Nila",
          lastName: "Sanja",
          hobbies: ["makan", "tidur", "mandi"],
        },
        {
          firstName: "Kiki",
          lastName: "Ratna",
          hobbies: ["makan", "tidur", "mandi"],
        },
        {
          firstName: "Ajeng",
          lastName: "Tsani",
          hobbies: ["makan", "tidur", "mandi"],
        },
      ],
      info: {
        name: "Sanja",
        company: "milispace",
        status: "ganteng",
      },
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
