<template>
  <div id="list">
    <h2>Completed Todos</h2>
    <ul>
      <CompletedItem 
        v-for="item in completedList" 
        v-bind:item="item"
        v-bind:key="item.id"/>
    </ul>
  </div>
</template>

<script>
  import CompletedItem from "./CompletedItem.vue";

  export default {
    props: ['completedList'], 
    components: {
      CompletedItem
    },
  }
</script>

<style>
</style>