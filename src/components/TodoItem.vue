<template>
  <li>
    {{ todo.title }}
    <button @click="$emit('removeTodo',todo.id)">&times;</button>
  </li>
</template>
<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
  
};
</script>
<style scoped>
    li{
        margin: 10px;
        border: 1px solid darkorange;
        
    }
</style>
