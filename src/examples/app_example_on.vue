<template>
  <p> {{ elem.content }} </p>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        content: 'this is some content',
      } 
    }, 
  }
</script>

<style>
  #app {
    display: flex;
  }
</style>