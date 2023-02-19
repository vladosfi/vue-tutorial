<template>
  <div>Picked: {{ picked }}</div>

  <input type="radio" id="BindingsExample" value="BindingsExample" v-model="picked" />
  <label for="BindingsExample">BindingsExample</label>
<p></p>
  <input type="radio" id="ListRendering" value="ListRendering" v-model="picked" />
  <label for="ListRendering">ListRendering</label>
<p></p>
  <input type="radio" id="MethodsAndEventHandling" value="MethodsAndEventHandling" v-model="picked" />
  <label for="MethodsAndEventHandling">MethodsAndEventHandling</label>
<p></p>
  <input type="radio" id="FormHandling" value="FormHandling" v-model="picked" />
  <label for="FormHandling">FormHandling</label>

  <p></p>

  <div v-if="picked === 'BindingsExample'">
    <BindingsExample />
  </div>
  <div v-if="picked === 'ListRendering'">
    <ListRendering />
  </div>
  <div v-if="picked === 'MethodsAndEventHandling'">
    <MethodsAndEventHandling />
  </div>
  <div v-if="picked === 'FormHandling'">
    <FormHandling />
  </div>
</template>

<script>
import BindingsExample from "./components/BindingsExample";
import ListRendering from "./components/ListRendering";
import MethodsAndEventHandling from "./components/MethodsAndEventHandling";
import FormHandling from "./components/FormHandling";

export default {
  name: "App",
  components: { BindingsExample, ListRendering, MethodsAndEventHandling, FormHandling },
  data() {
    return {
      picked: "BindingsExample",
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
