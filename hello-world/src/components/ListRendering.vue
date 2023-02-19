<template>
  <h1>List Rendering</h1>
  <div class="list">
    <h2 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h2>

    <h2 v-for="(name, index) in fullNames" :key="name.first">{{ index + 1 }} {{ name.first }} {{ name.last }}</h2>
  
    <div v-for="actor in actors" :key="actor.name">
      <h2>{{ actor.name }}</h2>
      <h4 v-for="movie in actor.movies" :key="movie">{{ movie }}</h4>
    </div>

    <h2 v-for="(value, key, index) in myInfo" :key="value">{{index}}. {{key}}: {{value}}</h2>

    <template v-for="name in names" :key="name">
      <h2 class="red"  v-if="name ===  'Brata'">{{ name }}</h2>
      <h2 class="green"  v-else>{{ name }}</h2>
      <hr>
    </template>
  </div>
</template>

<script>
export default {
  name: 'ListRendering',
  components: {},
  data() {
    return {
      names: ['Joro', 'Elena', 'Venci', 'Brata'],
      fullNames: [
        { first: 'Joro', last: 'Ivanov' },
        { first: 'Elena', last: 'Vasileva' },
        { first: 'Brata', last: 'Ivanov' },
      ],
      actors: [
        {
          name: 'Georgi Ivanov',
          movies: ['Vatman', 'Spiderman'],
        },
        {
          name: 'Vlado Ivanov',
          movies: ['Pakmen', 'ZigZagMan'],
        },
      ],
      myInfo: {
        name: 'Vlado',
        chennale: 'MacroSoft',
        course: 'Vue 3'
      }
    };
  },
};
</script>
<style>
.list {
  background-color: beige;
}
.red{
  background-color: red;
  color:chartreuse;
}
.green{
  background-color: olivedrab;
}
</style>
