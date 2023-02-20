<template>
  <div>
    <h2>Hello {{name}} a.k.a  {{heroName}}</h2>
  </div>
</template>

<script>
export default {
  name: "App",
  props: ['name','heroName'],
};
</script>

<style></style>
