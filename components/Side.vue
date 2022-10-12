<template>
  <aside class="Side">
    <div class="Side_Row">
      <h3 class="Side_Heading">
        <b-icon icon="tags"></b-icon>
        人気のタグ
      </h3>
      <ul class="PopularTags">
        <li v-for="tag in tags" :key="tag._id">
          <NuxtLink :to="`/blog/tag/${tag.slug}`"
            >{{ tag.name }}({{ tag.total }})</NuxtLink
          >
        </li>
      </ul>
    </div>
    <div class="Side_Row">
      <h3 class="Side_Heading">
        <b-icon icon="archive"></b-icon>
        アーカイブ
      </h3>
      <ul class="Archives">
        <li v-for="archive in archives" :key="archive.year">
          <NuxtLink :to="`/blog/archive/${archive.year}`"
            >{{ archive.year }}({{ archive.count }})</NuxtLink
          >
        </li>
      </ul>
    </div>
    <div class="Side_Row">
      <h3 class="Side_Heading">
        <b-icon icon="people"></b-icon>
        ライター
      </h3>
      <ul class="Writers">
        <li v-for="author in authors" :key="author._id">
          <NuxtLink :to="`/blog/author/${author.slug}`">
            <img
              v-if="author.profileImage && author.profileImage.src"
              :src="author.profileImage.src"
              :alt="author.fullName"
              width="32"
              height="32"
            />
            <div v-else class="Writers_Empty">
              <svg
                :title="author.fullName"
                xmlns="http://www.w3.org/2000/svg"
                width="18px"
                height="18px"
                viewBox="0 0 24 24"
                fill="#CCCCCC"
              >
                <path d="M0 0h24v24H0V0z" fill="none" />
                <path
                  d="M12 6c1.1 0 2 .9 2 2s-.9 2-2 2-2-.9-2-2 .9-2 2-2m0 10c2.7 0 5.8 1.29 6 2H6c.23-.72 3.31-2 6-2m0-12C9.79 4 8 5.79 8 8s1.79 4 4 4 4-1.79 4-4-1.79-4-4-4zm0 10c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"
                />
              </svg>
            </div>
          </NuxtLink>
        </li>
      </ul>
    </div>
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
