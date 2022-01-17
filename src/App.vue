<script>
import TodoApp from "./components/Todo/TodoList.vue";
export default {
  name: "app",
  components: {
    TodoApp,
  },
};
</script>

<template>
  <TodoApp></TodoApp>
</template>

<style>
#app {
}
body {
  margin: 0;
  padding: 0;
}
*{
  margin: 0;
  padding: 0;
}
</style>
