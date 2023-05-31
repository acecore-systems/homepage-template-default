<template>
  <section class="my-5 mx-lg-5 mx-3">
    <h3
      v-if="data.titleCopy"
      class="text-center mx-3"
    >{{data.titleCopy}}</h3>
    <p v-if="data.text" class="text-center mb-4 mx-3">{{data.text}}</p>
    <img
      v-if="data.image && data.image.src"
      :src="data.image.src"
      alt=""
      class="d-block object-fit-cover w-100 p-3"
      style="height: 25vw;"
    />
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
