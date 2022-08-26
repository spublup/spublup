<template>
  <div>
    <h1>Авторизация завершена</h1>
    <nuxt-link to="/" variant="success">Callback</nuxt-link>
  </div>
</template>
<script>
export default {
  middleware: ['auth'],
}
</script>
<style scoped>
</style>
