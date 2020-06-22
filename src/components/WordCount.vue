<template>
  <div v-if="wordsCounted > 1">Words: {{ wordsCounted }}
  </div>
  
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
        wordsCounted: "",
      }
    },


  computed: {
    countWords() {
      let vm = this;
      vm.str = vm.text;
      vm.str = vm.str.replace(/(^\s*)|(\s*$)/gi, "");
      vm.str = vm.str.replace(/[ ]{2,}/gi, " ");
      vm.str = vm.str.replace(/\n /, "\n");
      vm.wordsCounted = vm.str.split(" ").length;
      return vm.wordsCounted;
    }
  }
};
</script>

<style lang="scss" scoped>

</style>