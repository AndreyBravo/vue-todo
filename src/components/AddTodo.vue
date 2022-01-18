<template>
  <form @submit.prevent="onSubmit">
    <input v-model="title" type="text" />
  </form>
</template>
<script>
export default {
  data() {
    return {
      title: "",
    };
  },
  methods: {
    onSubmit() {
      if (this.title.trim()) {
        const newTodo = {
          id: Date.now(),
          title: this.title,
          done: false,
        };
        this.$emit("addTodo", newTodo);
        this.title = "";
      }
    },
  },
};
</script>