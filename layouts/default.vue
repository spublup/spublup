<template>
  <div>
    <header class="text-gray-600 body-font">
      <div class="container mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center">
        <nuxt-link to="/" class="flex title-font font-medium items-center text-gray-900 mb-4 md:mb-0">
          <span class="ml-3 text-xl">Spublup</span>
        </nuxt-link>
        <nav class="md:ml-auto flex flex-wrap items-center text-base justify-center">
          <nuxt-link to="/tts" class="mr-5 hover:text-gray-900">TTS</nuxt-link>
        </nav>
        <nuxt-link to="/login"
                   v-if="!this.$auth.loggedIn"
                   class="inline-flex items-center bg-gray-100 border-0 py-1 px-3 focus:outline-none hover:bg-gray-200 rounded text-base mt-4 md:mt-0">
          auth
          <svg fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
               class="w-4 h-4 ml-1" viewBox="0 0 24 24">
            <path d="M5 12h14M12 5l7 7-7 7"></path>
          </svg>
        </nuxt-link>
      </div>
    </header>
    <Nuxt/>
  </div>
</template>


<script>
export default {
  async beforeMount() {
    if (this.$auth.loggedIn) {
      const headers = {
        "Authorization": this.$auth.strategy.token.get(),
        "Client-Id": "ciq4tbgq90fztloi4ct96zjxyh7hnw"
      };
      const res = this.$axios.$get(
        `https://api.twitch.tv/helix/users`, {headers}
      ).then(response => {
        let user = response.data
        this.$auth.setUser(user[0])
      })
    }
  },
}
</script>
