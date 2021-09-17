<template>
  <p> {{ content }} </p>
  <button v-on:click="handleClick">Click me</button>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        content: 'this is some content',
      } 
    }, 
    methods: {
      handleClick () {
        this.content = 'this content changed'
      }
    }
  }
</script>

<style>
  #app {
    font-size: 72px;
  }
</style>