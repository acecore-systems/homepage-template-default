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
  background: url(https://cdn.discordapp.com/attachments/778104825845907457/1028837038604156968/kra-autosave.png);
  background-size: contain;
  width: 100%;
  height: 400;
}
.x-margin {
  background-color: white;
  /* 余白-右: 100px; */
  margin-right: 15%;
  /* 余白-左: 100px; */
  margin-left: 15%;
}
</style>