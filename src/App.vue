<template>
  <Quote qoute="Test Qoute" />
</template>

<script>
import { reactive } from "vue";
import Quote from "./components/Quote.vue";

export default {
  name: "App",
  components: {
    Quote,
  },
  setup() {
    const state = reactive({
      appStyle: {
        backgroundColor: "rgb(102, 51, 153)",
      },
    });

    return {
      state,
    };
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  font-family: "Raleway", sans-serif;
}
#app-wrapper {
  width: 100%;
  height: 100vh;
  background-color: rgb(102, 51, 153);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  -webkit-transition: all 1s ease-in-out;
  transition: all 1s ease-in-out;
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(5, 1fr);
  width: 100vw;
  height: 100vh;
}
</style>
