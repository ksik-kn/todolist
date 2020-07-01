<template>
  <div>
    <h1>{{ msg }}</h1>
    <to-do-list />
  </div>
</template>

<script>
import ToDoList from "./ToDoList.vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    ToDoList
  }
};
</script>

<style></style>
