<template>
  <div id="app">
    <Piano />
  </div>
</template>

<script>
import Piano from "./components/Piano.vue";

export default {
  name: "App",
  components: {
    Piano,
  },
};
</script>

<style lang="scss">
@import "./styles/main.scss";
</style>
