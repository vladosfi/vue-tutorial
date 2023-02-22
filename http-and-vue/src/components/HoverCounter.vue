<template>
  <div>
    <h2 @mouseover="incrementCount">Hovered {{ count }} times</h2>
  </div>
</template>

<script>
import CounterMixin from "../mixins/counter";

export default {
  name: "HoverCounter",
  mixins: [CounterMixin],
  // data() {
  //   return {
  //     count: 0,
  //   };
  // },
  // methods: {
  //   incrementCount() {
  //     return this.count++;
  //   },
  // },
};
</script>

<style scoped></style>
