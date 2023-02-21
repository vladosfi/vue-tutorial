<template>
  <div><h2>Component E</h2></div>
  <h3>Component E username {{ username }}</h3>
</template>

<script>
export default {
  name: "ComponentE",
  inject:['username']
};
</script>

<style scoped></style>
