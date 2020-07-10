<template>
  <div class="todo-item" v-bind:class="{ 'is-complete': todo.completed }">
    <p>
      <input type="checkbox" v-on:change="markComplete" />
      {{ todo.title }}
      <button @click="$emit('delete-todo', todo.id)" class="delete">
        &#10005;
      </button>
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
    },
  },
};
</script>

<style scoped>
.todo-item {
  padding: 1rem;
  border-bottom: solid 1px #ccc;
}

.is-complete p {
  text-decoration: line-through;
}

input[type="checkbox"] {
  margin-right: 0.5rem;
}

p {
  color: #b2b6d5;
  display: flex;
  align-items: center;
  justify-content: space-between;
  text-align: center;
}

button.delete {
  background: #fff;
  border: solid 2px #ff5a5f;
  border-radius: 100%;
  color: #464898;
  padding: 2px 4px;
  text-decoration: none;
}
</style>
