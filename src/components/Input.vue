<template>
  <input
    type="text"
    class="input"
    :value="inputData"
    :placeholder="placeholder"
    v-on:input="$emit('input', $event.target.value)"
  />
</template>

<script>
export default {
  name: "Input",
  props: {
    placeholder: {
      type: String,
      required: true
    },
    inputData: String
  }
};
</script>

<style lang="scss" scoped>
.input {
  padding: 5px;
  outline: none;
  font-size: 16px;
  border-radius: 5px;
  border: 2px solid #fff;
}
</style>
