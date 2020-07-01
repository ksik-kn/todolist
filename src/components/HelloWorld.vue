<template>
  <div>
    <h1>{{ msg }}</h1>
    <counter />
    <item-list />
    <to-do-list />
  </div>
</template>

<script>
import Counter from "./Counter.vue";
import ItemList from "./ItemList.vue";
import ToDoList from "./ToDoList.vue";

export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  components: {
    Counter,
    ItemList,
    ToDoList
  }
};
</script>

<style></style>
