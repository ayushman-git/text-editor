<template>
  <div>
    <textarea
      id="check"
      v-model="text"
      v-on:keydown.ctrl.down="decreaseFont"
      v-on:keydown.ctrl.up="increaseFont"
      v-on:keydown.ctrl.alt.w="changePadding"
      :style="{'font-size': fontSize+'px', 'padding-left': leftPadding+'%'}"
      type="text"
      autofocus
    />
    <TopBar class="topBar" />
    <BottomBar :text="text" />
  </div>
</template>

<script>
import BottomBar from './BottomBar'
import TopBar from "./TopBar";
export default {
  name: "Editor",
  components: { BottomBar, TopBar },

  data() {
    return {
      text: "",
      fontSize: 14,
      leftPadding: 2
    };
  },
  methods: {
    decreaseFont() {
      if (this.fontSize >= 10) this.fontSize -= 2;
    },
    increaseFont() {
      if (this.fontSize <= 26) this.fontSize += 2;
    },
    changePadding() {
      console.log('Check')
      if (this.leftPadding === 2) this.leftPadding = 25;
      else this.leftPadding = 2;
    }
  }
};
</script>

<style lang="scss" scoped>
$fontSize: 14px;

div {
  width: 100vh;
  overflow: hidden;
}

div textarea {
  position: relative;
  font-size: $fontSize;
  color: black;
  // height: 100vh;
  // width: 100%;
  outline: none;
  border: none;
  margin: 0;
  padding: 30px 10px 0px 10px;
  resize: none;
  font-family: "Courier New", Courier, monospace;
  background:transparent;
  // background: -webkit-linear-gradient(
  //   to right,
  //   #000000,
  //   #203a43,
  //   #0f2027
  // ); /* Chrome 10-25, Safari 5.1-6 */
  // background: linear-gradient(
  //   to right,
  //   #2c5364,
  //   #203a43,
  //   #0f2027
  // ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

.topBar {
  color: crimson;
  top: 0;
  margin: 0;
  position: absolute;
  background-color: #0f2027;
}
</style>