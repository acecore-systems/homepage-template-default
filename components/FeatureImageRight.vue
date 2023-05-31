<template>
  <section class="row mx-lg-5 mx-3 my-5">
    <div class="col-6">
      <h3 v-if="data.titleCopy">{{ data.titleCopy }}</h3>
      <p v-if="data.text">{{ data.text }}</p>
    </div>
    <div v-if="data.image && data.image.src" class="col-lg-6">
      <img :src="data.image.src" alt="" class="img-fluid w-100" />
    </div>
  </section>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      default() {
        return {
          titleCopy: '',
          text: '',
          image: null,
        }
      },
    },
  },
}
</script>
