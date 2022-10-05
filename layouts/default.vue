<template>
  <div class="main">
    <Header :app="app" />
    <Nuxt />
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  computed: {
    ...mapGetters(['app']),
  },
}
</script>

<style scoped>
.main {
  margin: 0, 100;
}
</style>