<template>
  <li id="listItem">
    <div id="todoContainer">
      <p id="todoContent">{{ todo.content }}</p>
      <button v-bind:id="todo.id" v-on:click="handleCompleted">&#10004;</button>
      <button v-bind:id="todo.id" v-on:click="handleDelete">&#10007;</button>
    </div>
  </li>
</template>

<script>
  export default {
    props: ['todo', 'handleCompleted', 'handleDelete'],
  }
</script>

<style>
  #listItem {
    list-style-type: none;
  }
  #todoContainer {
    padding: 10px;
    display: grid;
    grid-template-columns: auto auto auto;
  }

  #todoContainer > p {
    text-align: left;
  }

  #todoContainer > button {
    margin: 0px 2px 0px 2px;
    align-self: center;
  }

  #todoContent {
    width: 200px;
    word-wrap: break-word;
  }
</style>