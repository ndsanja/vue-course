<template>
  <div>Hello {{ name }}</div>
  <div v-text="name" />
  <div v-html="bold" />

  <div :id="headingId">Heading</div>
  <button :disabled="isDisabled">binding data</button>

  <h4 class="underline">underline text</h4>
  <h2 :class="status" class="underline">status</h2>
  <h2 :class="isPromoted && 'promoted'">Promoted</h2>
  <h2 :class="isSoldOut ? 'sold-out' : 'new'">Sold-out Movie</h2>

  <h2 :class="['new', 'promoted']">Newly promoted movie</h2>
  <h2 :class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">
    Newly promoted movie sold-out
  </h2>

  <h2
    :class="{
      promoted: isPromoted,
      new: !isSoldOut,
      'sold-out': isSoldOut,
    }"
  >
    Obj class binding conditional rendering
  </h2>
  <h2
    :style="{
      color: color,
      fontSize: headerSize + 'px',
      fontStyle: italic,
    }"
  >
    inline style
  </h2>

  <h2 :style="headerStyledObj">inline style with plain data</h2>
  <h2 :style="[headerStyledObj, backgroundColor]">
    array inline style with plain data css
  </h2>
</template>

<script>
export default {
  name: "BindingData",
  data() {
    return {
      name: "Sanja",
      bold: "<b>This is Html bold</b>",
      headingId: "heading",
      isDisabled: true,
      status: "success",
      isPromoted: true,
      isSoldOut: true,
      color: "orange",
      headerSize: 24,
      headerStyledObj: {
        color: "salmon",
        fontSize: "16px",
        fontStyle: "italic",
      },
      backgroundColor: {
        backgroundColor: "blue",
        color: "red",
      },
    };
  },
};
</script>

<style>
.success {
  color: blue;
}

.new {
  color: green;
}

.sold-out {
  color: red;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
