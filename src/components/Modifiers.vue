<template>
  <pre>
  {{ JSON.stringify(formValues, null, 2) }}
</pre
  >
  <form @submit.prevent="submitForm">
    <div>
      <label for="name">Name : </label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name" />
    </div>
    <br />
    <div>
      <label for="profile">Profile : </label>
      <textarea
        id="profile"
        v-model.lazy="formValues.profileSummary"
      ></textarea>
    </div>
    <br />
    <div>
      <label for="country">Country : </label>
      <select name="" id="country" v-model="formValues.country">
        <option value="">select country</option>
        <option value="Indonesia">Indonesia</option>
        <option value="Malaysia">Malaysia</option>
        <option value="Singapura">Singapura</option>
      </select>
    </div>
    <br />
    <div>
      <label for="job-location">Job Location : </label>
      <select
        name=""
        id="job-location"
        multiple
        v-model="formValues.jobLocation"
      >
        <option value="Indonesia">Indonesia</option>
        <option value="Malaysia">Malaysia</option>
        <option value="Singapura">Singapura</option>
      </select>
    </div>
    <br />
    <div>
      <input
        type="checkbox"
        name=""
        id="remote-work"
        v-model="formValues.remoteWork"
        true-value="yes"
        false-value="no"
      />
      <label for="remote-work">Available for remote work?</label>
    </div>
    <br />
    <div>
      <label> Skill Set : </label>
      <input
        type="checkbox"
        name=""
        id="html"
        value="html"
        v-model="formValues.skillSet"
      />
      <label for="html">HTML</label>
      <input
        type="checkbox"
        name=""
        id="css"
        value="css"
        v-model="formValues.skillSet"
      />
      <label for="css">CSS</label>
      <input
        type="checkbox"
        name=""
        id="js"
        value="js"
        v-model="formValues.skillSet"
      />
      <label for="js">JS</label>
    </div>
    <br />
    <div>
      <label> Years of Experience : </label>
      <input
        type="radio"
        name=""
        id="0-2"
        value="0-2"
        v-model="formValues.yearsOfExsperience"
      />
      <label for="0-2">0-2</label>
      <input
        type="radio"
        name=""
        id="3-5"
        value="3-5"
        v-model="formValues.yearsOfExsperience"
      />
      <label for="3-5">3 - 5</label>
      <input
        type="radio"
        name=""
        id="6-10"
        value="6-10"
        v-model="formValues.yearsOfExsperience"
      />
      <label for="6-10">6 - 10</label>
    </div>
    <br />
    <div>
      <label for="age">Age</label>
      <input
        @keyup.enter="submitForm"
        type="number"
        name=""
        id="age"
        v-model.number="formValues.age"
      />
    </div>
    <br />
    <!-- <div>
      <button type="submit">Submit</button>
    </div> -->
  </form>
</template>

<script>
export default {
  name: "Modifiers",
  data() {
    return {
      formValues: {
        name: "",
        profileSummary: "",
        country: "",
        jobLocation: [],
        remoteWork: "",
        skillSet: [],
        yearsOfExsperience: "",
        age: null,
      },
    };
  },
  methods: {
    submitForm() {
      console.log("Form Value", this.formValues);
      return this.formValues;
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
