<template>
  <div class="todo-list">
    <div v-bind:key="todo" v-for="todo in todos">
      <TodoItem
        v-bind:todo="todo"
        v-on:delete-todo="$emit('delete-todo', todo.id)"
      />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";
export default {
  name: "Todos",
  components: {
    TodoItem,
  },
  props: ["todos"],
};
</script>

<style scoped>
.todo-list {
  max-width: 407px;
  margin: 3rem auto;
  padding: 1.5rem;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  border-radius: 0.25rem;
}
</style>
