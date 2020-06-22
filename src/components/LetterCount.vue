<template>
  <div v-if="text">Letters: {{ text.length }}
  </div>
  
</template>

<script>
export default {
  name: 'LetterCount',
  props: {
    text: {
      type: String
    },
  },

    data() {
      return {
      }
    },
};
</script>

<style lang="scss" scoped>

</style>