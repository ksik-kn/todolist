<template>
  <div>
    <div>{{ countMessage }}</div>
    <button @click="count++">くりっく！</button>
    <button @click="count = 0">りせっと！</button>
  </div>
</template>

<script>
export default {
  name: "counter",
  data() {
    return {
      count: 0
    };
  },
  computed: {
    countMessage() {
      return "回数: " + this.count;
    }
  }
};
</script>

<style></style>