<template>
  <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete" />
      {{todo.title}}
      <button @click="$emit('delete-todo', todo.id)" class="delete">delete</button>
    </p>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.todo-item {
  padding: 1rem;
}

.is-complete {
  text-decoration: line-through;
}

input[type="checkbox"] {
  margin-right: 0.5rem;
}

p {
  color: #4e6e8e;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.delete {
  background: #ff5a5f;
  border: solid 1px #ff5a5f;
  border-radius: 0.25rem;
  color: #fff;
  padding: 2px;
  text-decoration: none !important;
}
</style>