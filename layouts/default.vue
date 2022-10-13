<template>
  <div class="Wrapper">
    <Header :app="app" :links="links" />
    <Nuxt />
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  computed: {
    ...mapGetters(['app','links']),
  },
}
</script>
