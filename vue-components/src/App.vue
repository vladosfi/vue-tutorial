<template>
  <div>
    <Greed name="VGI 1" heroName="Batman" />
    <Greed name="VGI 2" heroName="VatMan" />
    <Greed name="VGI 3" heroName="PacMan" />
    <Greed :name="name" :heroName="channel" />

    <ArticleComponent id="my-article" title="Art Title None default" :likes="25" :isPublished="isPublished" />

    //Provide and Inject
    <h3>App component username {{ uname }}</h3>
    <ComponentC />
  </div>
</template>

<script>
import Greed from "./components/Greed.vue";
import ArticleComponent from "./components/ArticleComponent.vue";
import ComponentC from "./components/ComponentC.vue";

export default {
  name: "App",
  components: {
    Greed,
    ArticleComponent,
    ComponentC,
  },
  data() {
    return {
      name: "Vladimir",
      channel: "Hero Devision",
      isPublished: true,
      uname: "VLADIMIR",
    };
  },
  provide() {
    return { username: this.uname };
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
