<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <input type="text" placeholder="Write a todo..." v-model="newTodo" />
    <button v-on:click="addTodo">Submit</button>

    <Todo
      v-for="(i, index) in todos"
      v-bind:key="index"
      v-bind:todo="i"
      v-on:delete="deleteTodo(index)"
    >
    </Todo>
  </div>
</template>

<script>
import Todo from "./components/Todo.vue";
export default {
  name: "App",
  components: {
    Todo,
  },
  data() {
    return {
      todos: ["Walk my cat", "Play games", "Eat"],
      newTodo: "",
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo === "") {
        alert("no");
        return;
      }
      this.todos.push(this.newTodo);
      this.newTodo = "";
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
