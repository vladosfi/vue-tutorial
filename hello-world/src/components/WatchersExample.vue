<template>
  <div>
    <h2>Volume Tracker (0-20)</h2>
    <h3>Current Volume - {{ volume }}</h3>
    <div>
      <button @click="volume += 2">Increase</button>
      <button @click="volume -= 2">Decrease</button>
    </div>
    <input type="text" v-model="movie" />
    <input type="text" v-model="movieInfo.title" />
    <input type="text" v-model="movieInfo.actor" />
  </div>
  <div>
    <button @click="movieList.push('Packman')">Add movie</button>
  </div>
</template>

<script>
export default {
  name: "WatchersExample",
  components: {},
  data() {
    return {
      volume: 0,
      movie: "",
      movieInfo: {
        title: "",
        actor: "",
      },
      movieList: ["batman", "superman"],
    };
  },
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert("Listening volume too high for a ling time");
      }
    },
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie name = ${newValue}`);
      },
      immediate: true,
    },
    movieInfo: {
      handler(newValue) {
        console.log(`Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`);
      },
      deep: true,
    },
    movieList: {
      handler(newValue) {
        console.log(`Updated list: ${newValue}`);
      },
      deep: true,
    },
  },
};
</script>
<style></style>
