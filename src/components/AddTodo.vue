<template>
  <form v-on:submit="addNew">
    <input v-model="title" type="text" name="newTodo"  placeholder="Add new todo">
    <button type="submit">Add</button>
  </form>
</template>

<script>
export default {
  name: "AddTodo",
  methods: {
    addNew(e){
      e.preventDefault();
      this.$emit("add-todo", this.title);
      this.title = "";
    }
  },
  data(){
    return {
      title: ""
    }
  }
}
</script>

<style>
  form{
    display: flex;
  }
  input{
    padding: 5px;
    flex: 3;
  }
  button{
    padding: 5px;
    flex: 1;
  }

</style>