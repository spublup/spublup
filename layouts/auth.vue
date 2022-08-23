<template>
  <div class="relative flex items-top justify-center min-h-screen bg-gray-100 auth-background">
    <Nuxt/>
  </div>
</template>

<script>
export default {
  name: "auth"
}
</script>

<style scoped>
.auth-background {
  background: url("~/assets/img/auth-background.svg"), #18191b;
}
</style>
