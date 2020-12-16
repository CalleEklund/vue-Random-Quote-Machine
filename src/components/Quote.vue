<template>
  <div id="wrapper">
    <div id="quote-box">
      <div id="text">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris sapien orci,
        placerat vitae eleifend at, gravida sit amet augue. Aliquam erat volutpat. Fusce
        condimentum scelerisque justo, eu blandit lacus egestas ut.
      </div>
      <div id="author">- Lorem Ipsum</div>
    </div>
    <button id="new-quote" :style="state.styleBg" @click="changeBgStyle">
      New Quote
    </button>
    <div id="footer">by Calle Eklund</div>
  </div>
</template>

<script>
import { reactive } from "vue";
export default {
  name: "Quote",
  props: {
    qoute: String,
    backgroundColor: String,
  },
  setup() {
    const state = reactive({
      styleBg: {
        backgroundColor: "rgb(248, 165, 194)",
        color: "white",
      },
    });

    function changeBgStyle() {
      const colorBg = "#" + ((Math.random() * 0xffffff) << 0).toString(16);
      this.state.styleBg = {
        backgroundColor: colorBg,
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
#wrapper {
  border: 1px solid #2d2d2d;
  grid-area: 2/ 2 / span 3 / span 3;
  display: inline-grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(5, 1fr);
  border-radius: 3px;
}
#quote-box {
  grid-area: 1/2 / span 3 / span 3;
  justify-self: stretch;
  align-self: center;
  font-size: 22px;
}
#text {
  padding-bottom: 5rem;
}
#new-quote {
  grid-row: 4;
  grid-column: 5;
  height: 5rem;
  width: 8rem;
  border: none;
  justify-self: center;
  align-self: center;
  border-radius: 5px;
  /**background-color: #d6c8c8;**/
  transition: 0.4s ease-out;
}
#new-quote:hover {
  cursor: pointer;
  /**background-color: rgb(78, 78, 158);**/
  transition: 0.4s ease-in;
  color: white;
  transform: scale(1.1, 1.1);
}
#footer {
  grid-area: 5/2 / span 3 / span 3;
  justify-self: center;
  align-self: end;
  padding-bottom: 15px;
}
</style>
