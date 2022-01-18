<template>
  <div id="app">
    <h1>Todo list</h1>
    <AddTodo @addTodo="addTodo" />
    <TodoList 
    :todos="todos" 
    @removeTodo="removeTodo"
    />
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
import AddTodo from "./components/AddTodo";

export default {
  name: "App",
  data() {
    return {
      todos: [
        { id: 1, title: "buy soil", done: false },
        { id: 2, title: "buy sugar", done: false },
        { id: 3, title: "buy apple", done: false },
      ],
    };
  },
  components: {
    TodoList,
    AddTodo,
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push(newTodo);
    },
    removeTodo(id){
      this.todos = this.todos.filter((t) => t.id !== id);
    }
  },
};
</script>

<style>
#app {
  margin: 100px 300px 100px 300px;

  text-align: center;
}
</style>
