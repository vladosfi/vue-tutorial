<template>
  <div>
    <h2>This is Popup</h2>
    <button @click="$emit('close','VGI passed back from child to parent component')">Close Popup</button>
  </div>
</template>

<script>
export default {
  name: "PopupExample",
  emits: ["close"],
};
</script>

<style scoped></style>
