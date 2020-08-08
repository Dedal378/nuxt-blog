<template>
  <div class="wrap mb-2">
    <span class="error mb-2">Ошибка 404</span>
    <nuxt-link to="/">Вернуться на главную</nuxt-link>
  </div>
</template>

<script>
  export default {
    name: "error"
  }
</script>

<style lang="scss" scoped>
  .wrap {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .error {
    color: red;
  }
</style>
