<template>
  <v-app>
    <div id="app">
      <router-view />
    </div>
  </v-app>
</template>

<script>
import "normalize.css";
export default {
  name: "App",
};
</script>

<style>
@import "./assets/css/styles.css";
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
