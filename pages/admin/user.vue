<template>
  <h1>user</h1>
</template>

<script>
  export default {
    name: "user",
    layout: 'admin',
    middleware: ['admin-auth'],
  }
</script>

<style lang="scss" scoped>

</style>
