<template>
  <!-- 背景を黒くして縦横を最大にする要素 -->
  <div class="full-size-background">
    <!-- 左右に余白を設けて背景が見えるようにする -->
    <div class="x-margin">
      <Header :app="app" />
      <Nuxt />
    </div>
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
.full-size-background {
  background-color: black;
}
.x-margin {
  background-color: white;
}
</style>