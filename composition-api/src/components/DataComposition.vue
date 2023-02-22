<template>
  <h2>Options - {{ o_firstName }}</h2>
  <h2>Options - {{ o_firstName }} {{ o_lastName }} a.k.a {{ o_heroName }}</h2>

  <br />
  <h2>Composition - {{ c_firstName }}</h2>
  <h2>Composition - {{ greet }}</h2>

  <h2>Composition - {{ c_firstName }} {{ c_lastName }} a.k.a {{ c_heroName }}</h2>
  <h2>Composition - {{ greetHero }}</h2>

  <br>
  //Reactive
  <h2>Composition - {{ state.firstName }} {{ state.lastName }} a.k.a {{ state.heroName }}</h2>
  <h2>Composition - {{ reactiveGreetHero }}</h2>

</template>

<script>
import { ref, reactive } from "vue";

export default {
  name: "DataComposition",
  setup() {
    const c_firstName = ref("Clark");
    const c_lastName = ref("Kent");
    const c_heroName = ref("Superman");

    //c_firstName.value = "Diana";
    const greet = `Hello ${c_firstName.value}`;
    const greetHero = `Hello ${c_lastName.value} ${c_lastName.value} a.k.a ${c_heroName.value}`;
    console.log("c_firstName", c_firstName);

    const state = reactive({
      firstName: "Princess",
      lastname: "Diana",
      heroName: "Wonder Women",
    });

    const reactiveGreetHero = `Hello ${state.firstName} ${state.lastname} a.k.a ${state.heroName}`;
    return {
      c_firstName,
      c_lastName,
      c_heroName,
      greet,
      greetHero,
      state,
      reactiveGreetHero,
    };
  },
  data() {
    return {
      o_firstName: "Bruce",
      o_lastName: "Wayne",
      o_heroName: "Batman",
    };
  },
};
</script>

<style scoped></style>
