<template>
  <div class="todo-item">
    <p>{{todo.title}}</p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"]
};
</script>

<style scoped>
.todo-item {
  padding: 1rem;
}
p {
  color: #4e6e8e;
}
</style>