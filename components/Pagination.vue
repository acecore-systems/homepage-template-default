<template>
  <nav class="Pagination">
    <ul class="Pagination_Items">
      <li v-for="page in pages" :key="page.number" class="Pagination_Item">
        <NuxtLink type="button" :to="`${basePath}/page/${page.number}`" :class="`Pagination_Button ${page.isCurrent ? '_current' : ''}`">{{page.number}}</NuxtLink>
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
.Pagination_Items{
    padding: 0 10px;
    list-style: none;
    font-size: 1.2rem;
    background-color: #6c7576;
    border: 1px solid #6c7576;
    border-radius: 4px;
    display: inline-block;
}
</style>