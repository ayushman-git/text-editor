<template>
  <input 
  type="text" 
  v-model="headerText" 
  @blur="onFocusOut"
  @click="onFocusIn"
  :style="{'text-align': textAlign}"
   />
</template>

<script>
export default {
  name: "TopBar",
  data() {
    return {
      headerText: "",
      textAlign: ""
    };
  },
  methods: {
        onFocusOut() {
              this.textAlign = 'center'
        },
        onFocusIn() {
              this.textAlign = 'left'
        }
  }
};
</script>

<style scoped>
input {
  padding: 3px;
  font-size: 16px;
  letter-spacing: 2px;
  text-align: left;
  border: none;
  outline: none;
  width: 100%;
}
</style>