<template>
  <div></div>
  <h2>{{ list.name }}</h2>
</template>

<script>
export default {
  name: "List",
  props: {
    list: Object,
  },
  data() {
    return {};
  },
};
</script>

<style scoped></style>
