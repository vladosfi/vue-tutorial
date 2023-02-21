<template>
  <div><h2>Component C</h2></div>
  <ComponentD />
</template>

<script>
import ComponentD from "./ComponentD.vue";

export default {
  name: "ComponentC",
  components: { ComponentD },
};
</script>

<style scoped></style>
