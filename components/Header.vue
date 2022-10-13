<template>
  <header class="navbar navbar-light bg-light">
    <div class="container">
      <NuxtLink to="/" class="navbar-brand">
        <span
          v-if="icon && icon.type === 'emoji' && icon.value"
          class="Title_Icon"
          >{{ icon.value }}
        </span>
        <span
          v-else-if="icon && icon.type === 'image' && icon.value"
          class="Title_Icon"
        >
          <img :src="icon.value" width="30" height="30" class="d-inline-block align-text-top" />
        </span>
        {{ title }}
      </NuxtLink>
      <div class="ms-auto">
        <a v-for="link in links" :key="link._id" :href="link.href" class="text-decoration-none text-muted ms-3">{{ link.text }}</a>
      </div>

    </div>
  </header>
</template>

<script>
export default {
  props: {
    app: {
      type: Object,
      default: null,
    },
    links: {
      type: Array,
      default: () => [],
    },
  },
  computed: {
    title() {
      return (this.app && (this.app.name || this.app.uid)) || 'Landing page'
    },
    icon() {
      return (this.app && this.app.icon) || { type: 'emoji', value: '🛬' }
    },
  },
}
</script>
