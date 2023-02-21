<template>
  <div><h2>Component D</h2></div>

  <ComponentE />
</template>

<script>
  import ComponentE from "./ComponentE.vue";

export default {
  name: "ComponentD",
  components: {ComponentE},
};
</script>

<style scoped></style>
