<template>
  <div>
    <div v-for="todo in todos" v-bind:key="todo.id">
      <TodoItem v-bind:Todo="todo" v-on:delete="$emit('delete', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from "./Todoitem";

export default {
  name: "Todos",
  components: {
    TodoItem
  },
  props: {
    "todos" : Array
  }
}
</script>

<style>

</style>