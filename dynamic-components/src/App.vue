<template>
  <button @click="activeTab = 'TabA'">Tab A</button>
  <button @click="activeTab = 'TabB'">Tab B</button>
  <button @click="activeTab = 'TabC'">Tab C</button>

  <!-- Keep the data on switching tabs -->
  <keep-alive>
    <component :is="activeTab" />
  </keep-alive>

  <!-- <TabA v-if="activeTab==='TabA'"/>
  <TabB v-if="activeTab==='TabB'"/>
  <TabC v-if="activeTab==='TabC'"/> -->

  <teleport to="#portal-root">
    <PortalComponent />
  </teleport>
</template>

<script>
import TabA from "./components/TabA.vue";
import TabB from "./components/TabB.vue";
import TabC from "./components/TabC.vue";
import PortalComponent from "./components/PortalComponent.vue";

export default {
  name: "App",
  components: {
    TabA,
    TabB,
    TabC,
    PortalComponent,
  },
  data() {
    return {
      activeTab: "TabA",
    };
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
