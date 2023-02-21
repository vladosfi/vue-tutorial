<template>
  <CardSlot></CardSlot>

  <CardSlot>Card content</CardSlot>
  <CardSlot><h2>Card content</h2></CardSlot>
  <CardSlot><h2>Card img</h2></CardSlot>

  <NamedSlots>
    <template v-slot:header>
      <h3>HEader</h3>
    </template>

    <template v-slot:default>
      <h3>Image src</h3>
    </template>

    <template v-slot:footer>
      <button>View Details</button>
    </template>
  </NamedSlots>

  //Slots Props
  <SlotsProps>
    <template v-slot:default="slotProps"> {{ slotProps.firstName }} {{ slotProps.lastName }} </template>
  </SlotsProps>
  <SlotsProps>
    <template v-slot:default="slotProps"> {{ slotProps.lastName }} {{ slotProps.firstName }} </template>
  </SlotsProps>
  <SlotsProps>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }}
    </template>
  </SlotsProps>
</template>

<script>
import CardSlot from "./components/CardSlot.vue";
import NamedSlots from "./components/NamedSlots.vue";
import SlotsProps from "./components/SlotsProps.vue";

export default {
  name: "App",
  components: {
    CardSlot,
    NamedSlots,
    SlotsProps,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
