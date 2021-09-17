<template>
  <p v-bind:class="className">{{ content }}</p>
  <button v-on:click="handleClick">Change Border Color</button>
</template>

<script>
  export default {
    name: 'App',
    data() {
      return {
        content: 'this is some content',
        className: 'greenBorder'
      }  
    },
    methods: {
      handleClick() {
        this.className = this.className === 'greenBorder'
          ? 'redBorder' 
          : 'greenBorder'
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