<template>
  <nav class="Pagination">
    <ul class="Pagination_Items">
      <div class="text-decoration-none"></div>
        <div class="btn btn-secondary"></div>
          <div class="px-3"></div>
            <div class="list-unstyled"></div>
              <div class="fs-3"></div>
                <div class="bg-secondary"></div>
                  <div class="border"></div>
                    <div class="rounded"></div>
                      <div class="d-inline-block"></div>
                        <div class="position-absolute"></div>
                          <div class="start-50"></div>
      <li v-for="page in pages" :key="page.number" class="Pagination_Item">
        <NuxtLink type="button" :to="`${basePath}/page/${page.number}`" :class="`Pagination_Button ${page.isCurrent ? '_current' : ''}`">{{page.number}}</NuxtLink>
      <div class="text-decoration-none"></div>
        <div class="btn btn-secondary"></div>
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

<style scoped>

.Pagination{
  padding: 10%;
}
</style>