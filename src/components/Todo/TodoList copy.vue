<template>
  <div>
    <h1>{{ name }}</h1>
    <h1>{{ email }}</h1>
    <!-- <ul>
      <li v-for="list in todoList">{{ list.name }}</li>
    </ul>
    <button v-on:click="buttonClick(1)">Click</button>
    <button @click="buttonClick(2)">Click</button>

    <input type="text" v-model="count" />
    <h2>{{ count }}</h2> -->

    <!-- Get Input From Input field -->
    <!--     <input v-model="name" type="text" />
    <br />
    <br />
    <input v-model="email" type="text" />
    <br />
    <br />
    <Button @click="createAlert()">Create Alert</Button> -->

    <!-- Send Parent to child data -->

    <input v-model="newData" />
    <br />
    <br />
    <button @click="addList(newData)">Button</button>
    <button @click="isTrue = !isTrue">Make ColorFull</button>

    <h6 v-for="list of todoList" :key="list.id">
      <list :class="{ textStyle: isTrue }" :todoList="list"></list>
    </h6>
  </div>
</template>

<script>
console.log("object");
import list from "./List.vue";
export default {
  name: "TodoList",
  components: {
    list: list,
  },
  data() {
    return {
      name: null,
      email: null,
      newData: null,
      count: 10,
      todoList: [
        { id: 1, name: "Done Electron" },
        { id: 2, name: "Done Core Concept of Vue.js" },
      ],

      isTrue: true,
    };
  },

  methods: {
    setTodoList(data) {
      todoList.push(data);
    },
    appendData(data) {
      console.log(this.email);
      return (this.email = data + this.email);
    },
    buttonClick(data) {
      alert("Button Pressed " + data);
    },
    createAlert() {
      alert(`
      Name: ${this.name}
      Email: ${this.email}`);
    },
    addList(data) {
      this.todoList = [...this.todoList, { name: data, id: Date.now() }];
      console.log(this.todoList);
    },
  },
};
</script>

<style scoped>
.textStyle {
  background-color: #26b63979;
}
</style>


