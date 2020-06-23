<template>
  <div>
    <textarea
      id="check"
      v-model="text"
      v-on:keydown.ctrl.down="decreaseFont"
      v-on:keydown.ctrl.up="increaseFont"
      :style="{'font-size': fontSize+'px'}"
      type="text"
      autofocus
    />
    <TopBar class="topBar" />
    <WordCount class="wordCount" :text="text" />
    <LetterCount class="letterCount" :text="text" />
  </div>
</template>

<script>
import WordCount from "./WordCount";
import LetterCount from "./LetterCount";
import TopBar from "./TopBar";
export default {
  name: "Editor",
  components: { WordCount, LetterCount, TopBar },

  data() {
    return {
      text: "",
      fontSize: 14
    };
  },
  methods: {
    decreaseFont() {
      if (this.fontSize >= 10) this.fontSize -= 2;
    },
    increaseFont() {
      if (this.fontSize <= 26) this.fontSize += 2;
    }
  }
};
</script>

<style lang="scss" scoped>
$fontSize: 14px;

div textarea {
  position: relative;
  font-size: $fontSize;
  color: white;
  height: 100vh;
  width: 100%;
  outline: none;
  border: none;
  margin: 0;
  padding: 30px 10px 0px 10px;
  resize: none;
  font-family: "Courier New", Courier, monospace;
  background: #0f2027; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #000000,
    #203a43,
    #0f2027
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #2c5364,
    #203a43,
    #0f2027
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

.wordCount {
  color: white;
  position: absolute;
  bottom: 0;
  right: 0;
}
.letterCount {
  color: white;
  position: absolute;
  bottom: 0;
  right: 100px;
}

.topBar {
  color: crimson;
  top: 0;
  margin: 0;
  position: absolute;
  background-color: #0f2027;
}
</style>