<template>
  <ComputedProperties />
  <VModel />
</template>

<script>
import VModel from "./components/VModel.vue";
import ComputedProperties from "./components/ComputedProperties.vue";

export default {
  name: "App",
  components: {
    VModel,
    ComputedProperties,
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
