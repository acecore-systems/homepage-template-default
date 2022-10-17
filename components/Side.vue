<template>
  <aside class="container">
    <h3>
      <b-icon icon="tags"></b-icon>
      人気のタグ
    </h3>
    <ul class="list-unstyled">
      <li v-for="tag in tags" :key="tag._id" class="mb-1">
        <NuxtLink :to="`/blog/tag/${tag.slug}`" class="ps-4 text-muted text-decoration-none"
          >{{ tag.name }}({{ tag.total }})</NuxtLink
        >
      </li>
    </ul>
    <h3>
      <b-icon icon="archive"></b-icon>
      アーカイブ
    </h3>
    <ul class="list-unstyled">
      <li v-for="archive in archives" :key="archive.year" class="mb-1">
        <NuxtLink :to="`/blog/archive/${archive.year}`" class="ps-4 text-muted text-decoration-none mb-3"
          >{{ archive.year }}({{ archive.count }})</NuxtLink
        >
      </li>
    </ul>
    <h3>
      <b-icon icon="people"></b-icon>
      ライター
    </h3>
    <ul class="list-unstyled">
      <li v-for="author in authors" :key="author._id" class="mb-1">
        <NuxtLink :to="`/blog/author/${author.slug}`" class="ps-4 text-muted text-decoration-none ">
          <img
            v-if="author.profileImage && author.profileImage.src"
            :src="author.profileImage.src"
            :alt="author.fullName"
            width="32"
            height="32"
          />
          <div v-else>
            <b-icon icon="person"></b-icon>
          </div>
        </NuxtLink>
      </li>
    </ul>
  </aside>
</template>

<script>
export default {
  props: {
    tags: {
      type: Array,
      default() {
        return []
      },
    },
    authors: {
      type: Array,
      default() {
        return []
      },
    },
    archives: {
      type: Array,
      default() {
        return []
      },
    },
  },
}
</script>
