<template>
  <div>
    <h1>Post List</h1>
    <button @click="getPosts">Load Posts</button>
    <h3 v-if="errorMessage">{{ errorMessage }}</h3>
    <div v-for="post in posts" :key="post.id">        
      <h3>{{ post.id }} {{ post.title }}</h3>
      <p>{{ post.body }}</p>
      <hr />
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "PostList",
  created() {
    this.getPosts();
  },
  data() {
    return {
      posts: [],
      errorMessage: "",
    };
  },
  methods: {
    getPosts() {
      axios
        .get("https://jsonplaceholder.typicode.com/posts")
        .then((x) => (this.posts = x.data))
        .catch(() => this.errorMessage = 'Error retrieving data');
    },
  },
};
</script>

<style scoped></style>
