<template>
  <button v-on:click="addItem" class="button">{{ name }}</button>
</template>

<script>
export default {
  name: "Button",
  props: {
    name: String,
    addItem: {
      required: true,
      type: Function
    }
  }
};
</script>

<style lang="scss" scoped>
.button {
  border: none;
  padding: 5px;
  color: #fff;
  outline: none;
  cursor: pointer;
  font-size: 16px;
  border-radius: 5px;
  background-color: #2c3e50;
  border: 2px solid #2c3e50;

  &:hover {
    background-color: #342224;
    border: 2px solid #342224;
  }
}
</style>
