<template>
  <div class="sm:flex container p-5 mx-auto content justify-betweenflex-wrap">
    <div class="view main-content w-full order-2">
      <div>Picked: {{ picked }}</div>

      <input type="radio" id="BindingsExample" value="BindingsExample" v-model="picked" />
      <label for="BindingsExample">Bindings Example</label>
      <p></p>
      <input type="radio" id="ListRendering" value="ListRendering" v-model="picked" />
      <label for="ListRendering">List Rendering</label>
      <p></p>
      <input type="radio" id="MethodsAndEventHandling" value="MethodsAndEventHandling" v-model="picked" />
      <label for="MethodsAndEventHandling">Methods And EventHandling</label>
      <p></p>
      <input type="radio" id="FormHandling" value="FormHandling" v-model="picked" />
      <label for="FormHandling">Form Handling</label>
      <p></p>
      <input type="radio" id="ComputedProperties" value="ComputedProperties" v-model="picked" />
      <label for="ComputedProperties">Computed Properties</label>
      <p></p>
      <input type="radio" id="WatchersExample" value="WatchersExample" v-model="picked" />
      <label for="WatchersExample">Watchers Example</label>

      <p></p>
      <input type="radio" id="ComponentsExample" value="ComponentsExample" v-model="picked" />
      <label for="ComponentsExample">Components Example</label>

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

      <div v-if="picked === 'ComputedProperties'">
        <ComputedProperties />
      </div>
      <div v-if="picked === 'WatchersExample'">
        <WatchersExample />
      </div>

            <div v-if="picked === 'ComponentsExample'">
        <ComponentsExample />
      </div>
    </div>
  </div>
</template>

<script>
import BindingsExample from "./components/BindingsExample";
import ListRendering from "./components/ListRendering";
import MethodsAndEventHandling from "./components/MethodsAndEventHandling";
import FormHandling from "./components/FormHandling";
import ComputedProperties from "./components/ComputedProperties";
import WatchersExample from "./components/WatchersExample";
import ComponentsExample from "./components/ComponentsExample";


export default {
  name: "App",
  components: { BindingsExample, ListRendering, MethodsAndEventHandling, FormHandling, ComputedProperties, WatchersExample,ComponentsExample },
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
