<template>
  <h3 v-for="name in names" :key="name.firstName">
    <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
  </h3>
</template>

<script>
export default {
  name: "SlotsProps",
  data() {
    return {
      names: [
        {
          firstName: "Ivan",
          lastName: "Draganov",
        },
        {
          firstName: "Al",
          lastName: "Bundy",
        },
        {
          firstName: "Open",
          lastName: "AI",
        },
      ],
    };
  },
};
</script>

<style scoped></style>
