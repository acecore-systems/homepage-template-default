<template>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <div class="post" v-html="body"></div>
  </main>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://ace.microcms.io/api/v1/blogs/${params.slug}`,
      {
        headers: { 'X-MICROCMS-API-KEY': '893ed44d45954ccd928384254dad5e1e1b48' } 
      }
    )
    return data
  }
}
</script>