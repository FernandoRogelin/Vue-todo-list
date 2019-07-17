<template>
  <div class="home">
    <div class="home-wrapper">
      <p class="home-title">Todo-list with VueJS</p>
      <div class="home-content">
        <Input placeholder="Write a text here" v-model="text" :inputData="text" />
        <Button :addItem="addItem" name="Add item" />
      </div>
      <ul class="home-result">
        <li v-for="(list, index) in lists" v-bind:key="list[list]" class="home-list">
          {{ list }}
          <span class="home-remove" v-on:click="removeItem(index)">X</span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Input from "@/components/Input.vue";
import Button from "@/components/Button.vue";

export default {
  name: "home",
  components: {
    Input,
    Button
  },
  data() {
    return {
      text: "",
      lists: []
    };
  },
  methods: {
    addItem() {
      this.lists.push(this.text);
    },
    removeItem(index) {
      this.lists.splice(index, 1);
    }
  }
};
</script>

<style lang="scss" scoped>
.home {
  display: flex;
  justify-content: center;

  &-wrapper {
    width: 500px;
    display: flex;
    margin-top: 50px;
    padding-top: 50px;
    min-height: 120px;
    border-radius: 10px;
    align-items: center;
    flex-direction: column;
    background-color: #ff6666;
    box-shadow: 15px 15px #e8e2e2 inset;
  }

  &-title {
    color: #fff;
    font-size: 20px;
    margin: 0 0 20px;
  }

  &-result {
    padding: 0;
    width: 100%;
  }

  &-list {
    display: flex;
    margin: 0 20px;
    padding: 10px 0;
    font-size: 18px;
    color: #ffffff;
    justify-content: space-between;

    &:not(:last-child) {
      border-bottom: 1px solid #afafaf;
    }
  }

  &-remove {
    color: #000;
    cursor: pointer;
  }
}
</style>
