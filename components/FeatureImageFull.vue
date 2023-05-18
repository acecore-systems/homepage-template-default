<template>
  <section class="my-5">
    <h3
      v-if="data.titleCopy"
      class="text-center"
      v-html="data.titleCopy"
    ></h3>
    <p v-if="data.text" class="text-center mb-4" v-html="data.text"></p>
    <img
      v-if="data.image && data.image.src"
      :src="data.image.src"
      alt=""
      class="d-block object-fit-cover px-lg-5 px-3 w-100"
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

<style>
.Feature1{
  overflow: hidden;
}
.Feature1_Image{
  width: auto;
}
</style>
