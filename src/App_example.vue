<template>
  <p>{{ content }}</p>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        content: 'this is some content stuff',
      }
    }, 
  }
</script>

<style>
  #app {
    display: flex;
    justify-content: center;
  }
</style>
