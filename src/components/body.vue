<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./todolist.vue";
import AddTodo from "../components/addtask.vue";

export default {
  name: "Body",
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todos: [],
    };
  },
  watch: {
    todos: {
      todos(newTodo, oldTodo) {},
    },
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
      const key = "todokey";
      let todo_string = localStorage.getItem(key);
      console.log(todo_string);
      let todo_obj = JSON.parse(todo_string);
      console.log(todo_obj);
      todo_obj.splice(id, 1);
      localStorage.setItem(key, JSON.stringify(todo_obj));
    },
    addTodo(newTodo) {
      const { id, title, completed } = newTodo;
      this.todos.push({ id, title, completed });
      localStorage.setItem("todokey", JSON.stringify(this.todos));
    },
    getTodo() {
      localStorage.getItem();
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

.btn {
  display: inline-block;
  border: none;
  background: #555;
  color: #fff;
  padding: 7px 20px;
  cursor: pointer;
}

.btn:hover {
  background: #666;
}
</style>
