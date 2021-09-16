<template>
  <Header/>
  <input v-model="todoInput"/>
  <button v-on:click="handleAdd">Add</button>
  <div id="container">
    <TodoList v-bind:todoList="todoList" v-bind:handleCompleted="handleCompleted"/>
    <CompletedList v-bind:completedList="completedList"/>
  </div>
</template>

<script>
import Header from './components/Header/Header.vue';
import TodoList from './components/Todo/TodoList.vue';
import CompletedList from './components/Completed/Completed.vue';

export default {
  name: 'App',
  data() {
    return {
      todoInput: '',
      todoList: [],
      completedList: [],
    }
  },
  methods: {
    handleAdd() {
      this.todoList.push({id: this.todoList.length, content: this.todoInput});
      this.todoInput = '';
    },
    handleCompleted(e) {
      this.todoList = this.todoList.filter((item) => {
        if (item.id === Number(e.target.id)) {
          this.completedList.push(item);
          return false;
        } else {
          return true;
        }
      })
    }
  },
  components: {
    Header,
    TodoList,
    CompletedList
  }
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }
  #app {
    height: 100%;
    margin: 0;
    padding: 0;
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  #container {
    margin-top: 10px;
    display: flex;
    justify-content: space-evenly;
  }

  #list {
    border-radius: 5%;
    border-style: solid;
    border-width: 1px;
    width: 400px;
    height: 800px;
    padding: 20px;
  }
</style>
