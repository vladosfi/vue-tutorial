<template>
  <div v-text="channel"></div>
  <div v-html="hacked"></div>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Bind</button>

  <h2 class="underline">Underlined text</h2>

  <h2 class="underline" v-bind:class="status">Status</h2>

  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>

  <h1 v-bind:class="isSoldout ? 'sold-out' : 'new'">Soldout?</h1>
  <h2 v-bind:class="['new', 'promoted']">Newly provided movie</h2>

  <h2 v-bind:class="[isPromoted && 'promoted', isSoldout ? 'sold-out' : 'new']">Array conditional movie</h2>
  <h2
    v-bind:class="{
      promoted: isPromoted,
      new: !isSoldout,
      'sold-out': isSoldout,
    }"
  >
    Object conditional movie
  </h2>

  <h2
    v-bind:style="{
      color: highlightColor,
      'font-size': headerSize + 'px',
      padding: '50px',
    }"
  >
    Inline style
  </h2>

  <h2 v-bind:style="headerStyleObject">Style object</h2>

  <h2 v-show="showElement">Using v-how element</h2>
  <h2 v-if="showElementIf">Using v-if element</h2>
</template>

<script>
export default {
  name: "BindingsExample",
  components: {},
  data() {
    return {
      name: "Jovaini",
      channel: "Codevolution",
      hacked: `<a href="#" onclick="alert('you have been hacked!')">Win a prise!</a>`,
      headingId: "heading",
      isDisabled: true,
      status: "success",
      isPromoted: true,
      isSoldout: true,
      highlightColor: "orange",
      headerSize: 50,
      headerStyleObject: {
        color: "orange",
        fontSize: "10px",
        padding: "10px",
      },
      showElement: false,
      showElementIf: false,
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

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}

.new {
  color: olivedrab;
}

.sold-out {
  color: red;
}
</style>
