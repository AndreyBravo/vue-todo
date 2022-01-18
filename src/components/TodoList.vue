<template>
  <ul>
    <TodoItem
      v-for="todo in todos"
      :key="todo.id"
      :todo="todo"
      @removeTodo="removeTodo"
    />
  </ul>
</template>

<script>
import TodoItem from "./TodoItem";

export default {
  props: ["todos"],
  components: {
    TodoItem,
  },
  methods: {
    removeTodo(id) {
      this.$emit("removeTodo", id);
    },
  },
};
</script>
<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>