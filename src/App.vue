<template>
  <Header/>
  <TodoList/>
  <CompletedList/>
</template>

<script>
import Header from './components/Header/Header.vue';
import TodoList from './components/Todo/TodoList.vue';
import CompletedList from './components/Completed/Completed.vue';

export default {
  name: 'App',
  components: {
    Header,
    TodoList,
    CompletedList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
