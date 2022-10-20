<template>
  <!-- 背景を黒くして縦横を最大にする要素 -->
  <div class="full-size-background">
    <!-- 左右に余白を設けて背景が見えるようにする -->
    <div class="x-margin">
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
.full-size-background {
  background: url(https://cdn.discordapp.com/attachments/778104825845907457/1028837038604156968/kra-autosave.png);
  background-size: cover;
}
.x-margin {
  margin: 0 15%;

  background-color: rgba(255, 255, 255, 0.8);
}
</style>