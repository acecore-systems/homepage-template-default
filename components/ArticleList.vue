<template>
  <div class="Articles">
  <Dropdown :categories="categories" />
  <div class="Inner">
    <ArticleCard
      v-for="article in articles"
      :key="article._id"
      :article="article"
    />
  </div>
  <Pagination :total="total" :current="1" />
</div>
</template>

<script>
  export default {}
</script>

<style scoped>
  .Articles {
    padding: 24px 24px 40px 24px;
    margin: 0 auto;
  }
  .Inner {
    display: flex;
    flex-wrap: wrap;
  }
  @media (min-width: 600px) {
    .Articles {
      padding: 60px;
    }
  }
  @media (min-width: 960px) {
    .Articles {
      max-width: 1024px;
    }
  }
  </style>
