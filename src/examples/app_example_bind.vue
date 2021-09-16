<template>
  <p v-bind:class="className">{{ content }}</p>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        content: 'this is some content',
        className: 'greenBorder'
      }  
    } 
  }
</script>

<style>
  #app {
    font-size: 72px;
  }
  .redBorder {
    border-style: solid;
    border-width: 10px;
    border-color: red;
    font-family: Arial, Helvetica, sans-serif;
  }
  .greenBorder {
    border-style: solid;
    border-width: 10px;
    border-color: green;
    font-family: Arial, Helvetica, sans-serif;
  }
</style>