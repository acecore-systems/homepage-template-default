<template>
  <nav class="p-5">
    <ul
      class="px-0 list-unstyled fs-0.5 bg-secondary border rounded d-inline-block position-absolute start-50">
      <li v-for="page in pages" :key="page.number" class="Pagination_Item">
        <NuxtLink
          type="button" 
          :to="`${basePath}/page/${page.number}`"
          :class="`text-decoration-none btn btn-secondary ${page.isCurrent ? '_current' : ''}`"
        >{{ page.number }}</NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  props: {
    total: {
      type: Number,
      default: 0,
    },
    current: {
      type: Number,
      default: 1,
    },
    basePath: {
      type: String,
      default: '',
    }
  },
  computed: {
    pages() {
      return Array(Math.ceil(this.total / (this.$config.pageLimit || 10)))
        .fill({ number: 0, isCurrent: false })
        .map((value, index) => {
          const pageNumber = index + 1
          return {
            ...value,
            number: pageNumber,
            isCurrent: this.current === pageNumber
          }
        })
    }
  }
}
</script>