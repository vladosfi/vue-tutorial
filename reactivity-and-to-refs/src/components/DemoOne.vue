<template>
  <div>
    <h2>{{ name }}</h2>
  </div>
</template>

<script>
import {ref} from 'vue'
export default {
  name: "DemoOne",
  setup() {
    const name = ref("Vladimir");

    setTimeout(() => {
      name.value = 'New name'
    }, 2000);

    return {
      name,
    };
  },
};
</script>
<style lang="scss" scoped></style>
