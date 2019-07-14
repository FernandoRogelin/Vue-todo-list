<template>
  <div class="home">
    <div class="home-wrapper">
      <p class="home-title">Todo-list with VueJS</p>
      <div class="home-content">
        <Input placeholder="Write a text here" v-model="text" :inputData="text" />
        <Button :addItem="addItem" name="Add item" />
      </div>
      <ul class="home-result">
        <li v-for="list in lists" v-bind:key="list[list]" class="home-list">
          {{ list }}
          <span v-on:click="removeItem(list)">X</span>
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
    removeItem(item) {
      console.log(item);
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
    display: block;
    margin: 0 20px;
    padding: 10px 0;
    font-size: 18px;
    color: #2e4852;

    &:not(:last-child) {
      border-bottom: 1px solid #afafaf;
    }
  }
}
</style>
