<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" name="title" placeholder="Title" />
      <input type="submit" value="Add Todo" class="btn" />
    </form>
  </div>
</template>

<script>
// import uuid from "uuid";
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false,
      };
      //send up to parent
      this.$emit("add-todo", newTodo);
      this.title = "";
    },
  },
};
</script>

<style scoped>
input[type="text"] {
  margin-right: 0.5rem;
  padding: 0.2rem;
  border-radius: 0.25rem;
  border: solid 1px #fff;
}

input.btn {
  background-color: #4fc08d;
  padding: 3px;
  border: solid 1px #4fc08d;
  border-radius: 0.25rem;
  color: #fff;
}
</style>
