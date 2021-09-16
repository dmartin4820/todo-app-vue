<template>
  <div id="list">
    <h2>Todo List</h2>
    <ul>
      <TodoItem 
        v-for="todo in todoList" 
        v-bind:todo="todo" 
        v-bind:key="todo.id"
        v-bind:handleCompleted="handleCompleted"
        v-bind:handleDelete="handleDelete"/>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

  export default {
    props: ['todoList', 'handleCompleted', 'handleDelete'],
    components: {
      TodoItem
    }
  }
</script>

<style>
  #list > h2 {
    margin-bottom: 30px;
  }

  #list > input {
    margin: 5px;
  }

  #list > button {
    padding: 2px;
  }
</style>