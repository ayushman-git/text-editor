<template>
  <div>{{ text }}</div>
</template>

<script>
export default {
  name: 'WordCount',
  props: {
    text: {
      type: String
    },
  },

    data() {
      return {
        str: "",
      }
    },

  watch: {
    countWords() {
      this.str = this.text;
      this.str = this.str.replace(/(^\s*)|(\s*$)/gi, "");
      this.str = this.str.replace(/[ ]{2,}/gi, " ");
      this.str = this.str.replace(/\n /, "\n");
      this.str = this.str.split(" ").length;
    }
  }
};
</script>

<style lang="scss" scoped>

</style>