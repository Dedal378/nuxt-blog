<template>
  <h1>logout</h1>
</template>

<script>
  export default {
    name: "logout",
    layout: 'admin',
    middleware: ['admin-auth'],
  }
</script>

<style lang="scss" scoped>

</style>
