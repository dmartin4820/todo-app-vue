<template>
  <p 
    v-for="elem in elements" 
    v-bind:key="elem.id"
  >
    {{ elem.content }}
  </p>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        content: 'this is some content',
        show: true,
        elements: [
          {id: 0, content:'this is the first thing'},
          {id: 1, content:'this is the second thing'},
          {id: 2, content:'this is the third thing'}
        ]
      }
    }, 
  }
</script>

<style>
  #app {
    display: flex;
    flex-direction: column;
    font-size: 72px;
  }
</style>
