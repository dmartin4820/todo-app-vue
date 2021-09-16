<template>
  <li id="completedItem">
    <div id="completedContainer">
      <p id="completedContent">{{ item.content }}</p>
    </div>
  </li>
</template>

<script>
  export default {
    props: ['item']
  }
</script>

<style>
  #completedItem {
    list-style-type: none;
  }
  #completedContainer {
    display: flex;
    justify-content: center;
  }
</style>