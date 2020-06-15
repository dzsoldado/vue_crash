<template>
  <div class="item" v-bind:class="{'completed':Todo.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      {{Todo.title}}
      <button class="btn" @click="$emit('delete', Todo.id)">x</button>
    </p>
  </div>
</template>

<script>

export default {
  name: "TodoItem",
  props: {
    Todo: Object
  },
  methods: {
    markComplete(){
      this.Todo.completed = !this.Todo.completed ;
    }
  }
}
</script>

<style scoped>
  .item{
    background: #ccc;
    padding: 10px;
    border-bottom: 1px solid #666;
  }
  .completed{
    text-decoration: line-through;
  }
  .btn{
    padding: 5px 9px;
    color: white;
    background-color: #f00;
    border: none;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
</style>

