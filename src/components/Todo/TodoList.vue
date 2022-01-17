<template>
  <div class="todoContainer">
    <div class="innerContainer">
      <h1 class="todo-header">To Do List</h1>
      <br />
      <input type="text" class="todo-input" v-model="newData" />
      <button @click="addList(newData)" class="todo-button">Add</button>

      <ul>
        <li v-for="item of list" :key="item.id">
          <List :list="item" />
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import List from "./List.vue";
export default {
  name: "TodoApp",
  components: {
    List,
  },
  data() {
    return {
      newData: null,
      list: [],
    };
  },
  methods: {
    addList(data) {
      this.list = [...this.list, { id: Date.now(), name: data }];
    },
    removeTodo(id) {
      return id;
    },
  },
  components: { List },
};

// const isDev = process.env.IS_DEV == "true" ? false : true;

console.log(import.meta.env.IS_DEV, "boshoto");
</script>

<style scoped>
.todoContainer {
  background-image: linear-gradient(60deg, #fbc7d4, #9796f0);
  min-height: 100vh;
  margin: 0 auto;
  text-align: center;
}
.innerContainer {
  width: 565px;
  margin: 0 auto;
  position: relative;
}
.todo-header {
  text-align: center;
  padding-top: 2rem;
}
.todo-button {
  font-size: 1.5rem;
  padding: 0.5rem 1rem;
  border: none;
  left: -74px;
  cursor: pointer;
  position: relative;
  background: none;
  border-radius: 0.2rem;
  transition: all 0.4s;
}
.todo-button:hover {
  background: black;
  color: white;
}
.todo-input {
  outline: none;
  border: none;
  font-size: 1.5rem;
  padding: 0.5rem 5rem 0.5rem 0.5rem;
  color: #34495e;
  border-radius: 0.2rem;
  width: 400px;
  word-wrap: break-word;
}
li {
  list-style: none;
  text-align: left;
  background-color: #9796f06e;
  margin: 1rem 0;
  padding: 0.2rem;
  border-radius: 0.2rem;
}
</style>
