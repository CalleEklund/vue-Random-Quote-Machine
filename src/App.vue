<template>
  <div id="wrapper">
    <Quote qoute="Test Qoute" />
  </div>
</template>

<script>
import Quote from "./components/Quote.vue";

export default {
  name: "App",
  components: {
    Quote,
  },
};
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
}
#wrapper {
  width: 100%;
  height: 100vh;
 
}
#app {
  background-color: rebeccapurple;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
