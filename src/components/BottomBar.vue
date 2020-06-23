<template>
  <div>
    <WordCount class="wordCount" :text="text" />
    <LetterCount class="letterCount" :text="text" />
  </div>
</template>

<script>
import LetterCount from "./LetterCount";
import WordCount from "./WordCount";
export default {
  name: "BottomBar",
  components: { LetterCount, WordCount },
  props: {
        text: {
              type: String,
        }
  }
};
</script>

<style scoped>
.wordCount {
  position: absolute;
  bottom: 0;
  right: 0;
}
.letterCount {
  position: absolute;
  bottom: 0;
  right: 100px;
}
</style>