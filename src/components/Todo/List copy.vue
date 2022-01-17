<template>
  <div>
    <h3>Name {{ todoList.name }}</h3>


    <!-- <h3 v-for="list of testList" :key="list.id">{{ list.name }}</h3> -->
  </div>
</template>

<script>
export default {
  name: "list",
  props: {
    name: String,
    todoList: Object,
  },
  data() {
    return {
      name2: "Single List",
    };
  },
};
</script>

<style scoped>

</style>
