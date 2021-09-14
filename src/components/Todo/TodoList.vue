<template>
  <div>
    <input v-model="input"/>
    <button v-on:click="handleAdd">Add</button>
    <ul>
      <TodoItem v-for="todo in todoList" v-bind:todo="todo" v-bind:key="todo.id"/>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';

  export default {
    data() {
      return {
        input: '',
        todoList: []
      }
    },
    methods: {
      handleAdd() {
        this.todoList.push({id: this.todoList.length, content: this.input});
        this.input = '';
      }
    },
    components: {
      TodoItem
    }
  }
</script>