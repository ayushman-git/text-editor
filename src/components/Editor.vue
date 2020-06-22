<template>
  <div>
    <textarea v-model="text" type="text" autofocus />
    <WordCount class="wordCount" :text="text" />
  </div>
</template>

<script>
import WordCount from './WordCount'
export default {
  name: "Editor",
  components: { WordCount },

  data() {
    return {
      text: ""
    };
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
div textarea {
  position: relative;
  color: white;
  height: 100vh;
  width: 100%;
  outline: none;
  border: none;
  margin: 0;
  padding: 0;
  resize: none;
  font-family: "Courier New", Courier, monospace;
  background: #0f2027; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #2c5364,
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
  position: absolute;
}
</style>