<template>
  <div>{{ add() }}</div>
  <div>{{ addWithParams(3, 5, 7) }}</div>
  <div>Multiply - {{ multiply(3) }}</div>

  <h2>{{ name }}</h2>
  <div>
    <button v-on:click="name = 'batman'">Change Name</button>
  </div>

  <h2>{{ count }}</h2>
  <button v-on:click="increment(3)">Increment 3</button>
  <button v-on:click="decrement(5)">Decrement 5</button>
<p></p>
  <button @click="increment(3), decrement(5)">Increment 3</button>
  <button @click="decrement(5)">Decrement 5</button>
</template>

<script>
export default {
  name: "MethodsAndEventHandling",
  components: {},
  data() {
    return {
      baseMultiplier: 5,
      name: "Vlado",
      count: 0,
    };
  },
  methods: {
    add() {
      return 2 + 3 + 5;
    },
    addWithParams(a, b, c) {
      return a + b + c;
    },
    multiply(num) {
      return num * this.baseMultiplier;
    },
    decrement(num) {
      this.count -=num;
    },
    increment(num) {
      this.count += num;
    },
  },
};
</script>
<style></style>
