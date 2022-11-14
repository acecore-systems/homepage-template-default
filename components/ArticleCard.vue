<template>
  <NuxtLink v-if="article" class="text-decoration-none" :to="`/blog/article/${article.slug}`">
    <div class="row">
      <div class="col-5">
        <template v-if="article.coverImage">
          <img :src="article.coverImage.src" class="samenaleimg" alt="" width="300" height="200"/>
        </template>
        <template v-else>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="40px"
            height="40px"
            viewBox="0 0 24 24"
            fill="#CCCCCC"
          >
            <path d="M0 0h24v24H0V0z" fill="none" />
            <path
              d="M19 5v14H5V5h14m0-2H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-4.86 8.86l-3 3.87L9 13.14 6 17h12l-3.86-5.14z"
            />
          </svg>
        </template>
      </div>
      <div class="col-7">
        <div class="card-body">
          <h3 class="card-title">{{ article.title }}</h3>
          <ul class="card-text">
            <li v-for="tag in article.tags" :key="tag._id">#{{ tag.name }}</li>
          </ul>
          <div class="row-two">
            <div class="col-2">
              <template v-if="article.author && article.author.profileImage">
              <img
                :src="article.author.profileImage.src"
                alt=""
                width="32"
                height="32"
              />
            </template>
            <template v-else>
              <div class="card-text">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="20px"
                  height="20px"
                  viewBox="0 0 24 24"
                  fill="#CCCCCC"
                >
                  <path d="M0 0h24v24H0V0z" fill="none" />
                  <path
                    d="M12 6c1.1 0 2 .9 2 2s-.9 2-2 2-2-.9-2-2 .9-2 2-2m0 10c2.7 0 5.8 1.29 6 2H6c.23-.72 3.31-2 6-2m0-12C9.79 4 8 5.79 8 8s1.79 4 4 4 4-1.79 4-4-1.79-4-4-4zm0 10c-2.67 0-8 1.34-8 4v2h16v-2c0-2.66-5.33-4-8-4z"
                  />
                </svg>
              </div>
            </template>
            </div>
            <div class="col-three">
              <div class="row-three">
                {{ authorName }}
              </div>
              <div class="row-three">
                <time
                  :datetime="formatDate(article._sys.createdAt).replace(/\//gm, '-')"
                  >{{ formatDate(article._sys.createdAt) }}</time
                >
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </NuxtLink>
</template>

<script>
import { formatDate } from 'utils/date'

export default {
  props: {
    article: {
      type: Object,
      default: null,
    },
  },
  computed: {
    authorName() {
      return (this.article.author && this.article.author.fullName) || 'NO NAME'
    },
  },
  methods: {
    formatDate(dateStr) {
      return dateStr ? formatDate(dateStr) : ''
    },
  },
}
</script>

<style scoped>
.samenaleimg {
  width: 300px;
  height: 200px;
  margin: 50px 0 50px 0;
  object-fit: cover;
  object-position: 50;
  border-radius: 8px;
}
.card-text {
  color: #6c757d;
  padding: 0%;
}
.col-2 {
  padding: 0% ;
}
.row-two {
  
}
.card-text li {
    margin: 0 12px 0 0;
    padding: 0 5px;
    list-style: none;
    font-size: 1.2rem;
    color: #888;
    border: 1px solid #e5e5e5;
    border-radius: 4px;
    display: inline-block;
}
.col-7 {
  margin-top: 50px;
  border-bottom: none;
}
.card-title {
  color: #313131;
}
.card-body {
  color: #6c757d;
}
.row {
  border-bottom: 1px solid #ccc;
}
.row-two {
  margin-top: -40px;
}
.row-three {
}
svg {
  background: rgb(243, 243, 243);
  border-radius: 50px;
  margin-top: 50px;
}
</style>