<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todos" v-on:delete="del" /> 
    <AddTodo v-on:add-todo="add"/>
  </div>

</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/layout/Header";
import AddTodo from "./components/AddTodo";

export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo
  },
  methods:{
    del(id){
      this.todos = this.todos.filter(todo=>todo.id!==id);
    },
    add(title){
      this.todos.push({id: this.todos.length+1, title:title, completed:false})
    }
  },
  data(){
    return {
      todos: [
        {
          id: 1,
          title: "lorem epsum",
          completed: false
        },
        {
          id: 2,
          title: "dolor sit amet consectetur adipisicing elit",
          completed: true
        },
        {
          id: 3,
          title: "Ducimus sequi",
          completed: false
        }
      ]
    }
  }
}
</script>

<style>

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body{
  text-rendering: optimizeLegibility;
  overflow-x: hidden;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
