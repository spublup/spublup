<template>

</template>

<script>
export default {
  middleware: 'auth',
  name: "tts",
  mounted() {
    console.log(this.$auth.user)
  }
}
</script>

<style scoped>

</style>
