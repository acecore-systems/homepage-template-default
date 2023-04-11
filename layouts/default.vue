<template>
  <div class="full-size-background pb-1" :style="{ backgroundImage: 'url(' + app.cover.value + ')' }">
    <div class="x-margin pb-1">
      <Header :app="app" :links="links" />
      <Nuxt />
    </div>
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

<style scoped>
html, body, header,.full-size-background {
  height: 100%;
}
.full-size-background {
  background-size: cover;

}
.x-margin {
  margin: 0 15%;
  margin-bottom: 15%;
  background-color: rgba(255, 255, 255, 0.9);
}
@media screen and (max-width: 480px) {
  .x-margin{
    margin:0 5vw;
  }
}
</style>