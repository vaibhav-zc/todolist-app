<template>
  <div>
    <form @submit.prevent="addTodo">
      <input
        type="text"
        v-model="title"
        name="title"
        placeholder="Add Todo  "
      />
      <input type="submit" value="Add" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      id: 1,
      title: "",
    };
  },
  methods: {
    addTodo() {
      const newTodo = {
        id: this.id,
        title: this.title,
        completed: false,
      };
      this.id += 1;
      // Send up to parent

      this.$emit("add-todo", newTodo);
      this.title = "";
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 5;
  padding: 5px;
  font-size: 30px;
  outline: none;
  padding: 4px;
}

input[type="submit"] {
  flex: 2;
  background-color: #395b64;
  color: white;
  font-size: 30px;
  outline: none;
  border: none;
  padding: 4px;
}

input[type="submit"]:hover {
  background-color: #a5c9ca;
}
</style>


