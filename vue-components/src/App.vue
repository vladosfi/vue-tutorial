<template>
  <div>
    <Greed name="VGI 1" heroName="Batman" />
    <Greed name="VGI 2" heroName="VatMan" />
    <Greed name="VGI 3" heroName="PacMan" />
    <Greed :name="name" :heroName="channel" />

    <ArticleComponent id="my-article" title="Art Title None default" :likes="25" :isPublished="isPublished" />

    //Provide and Inject
    <br>
    <h3>App component username {{ uname }}</h3>
    <ComponentC />

    //Popup Example
    <br>
    <button @click="showPopup = true">Show Popup</button>
    <PopupExample v-show="showPopup" @close="closePopup" />
  </div>
<br>
  //Components and v-model
  <br>
  <InputVmodel v-model="vModelNameProp"/>
</template>

<script>
import Greed from "./components/Greed.vue";
import ArticleComponent from "./components/ArticleComponent.vue";
import ComponentC from "./components/ComponentC.vue";
import PopupExample from "./components/PopupExample.vue";
import InputVmodel from "./components/InputVmodel.vue";

export default {
  name: "App",
  components: {
    Greed,
    ArticleComponent,
    ComponentC,
    PopupExample,
    InputVmodel,
  },
  data() {
    return {
      name: "Vladimir",
      channel: "Hero Devision",
      isPublished: true,
      uname: "VLADIMIR",
      showPopup: false,
      vModelNameProp: "",
    };
  },
  provide() {
    return { username: this.uname };
  },
  methods: {
    closePopup(name) {
      this.showPopup = false;
      console.log(name);
    },
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
