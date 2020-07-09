<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
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

.is-complete {
  text-decoration: line-through;
}

p {
  color: #4e6e8e;
}
</style>