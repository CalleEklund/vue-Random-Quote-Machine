<template>
  <div id="wrapper">
    <div id="quote-box" :style="state.styleBg">
      <div id="text"></div>
      <div id="author"></div>
      <button id="new-quote" @click="changeBgStyle">New Quote</button>
    </div>
    <div id="footer">by Calle Eklund</div>
  </div>
</template>

<script>
import { reactive } from "vue";
export default {
  name: "Quote",
  props: {
    qoute: String,
  },
  setup() {
    const state = reactive({
      styleBg: {
        backgroundColor: "rgb(248, 165, 194)",
      },
    });

    function changeBgStyle() {
      this.state.styleBg = {
        backgroundColor: "#" + ((Math.random() * 0xffffff) << 0).toString(16),
      };
    }
    return {
      state,
      changeBgStyle,
    };
  },
};
</script>

<style scoped>
body,
button {
  -webkit-transition: all 0.4s ease-in-out;
  transition: all 0.4s ease-in-out;
}
#quote-box {
  width: 500px;
  height: 300px;
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  border: 5px solid #ffff00;
  padding: 20px;
}
</style>