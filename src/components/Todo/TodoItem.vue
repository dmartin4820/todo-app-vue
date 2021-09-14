<template>
  <li>{{ todo.content }}</li>
</template>

<script>
  export default {
    props: ['todo'],
  }
</script>