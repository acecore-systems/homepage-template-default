<template>
  <section class="Feature1">
    <h3
      v-if="data.titleCopy"
      class="Feature1_Title text-center"
      v-html="data.titleCopy"
    ></h3>
    <p v-if="data.text" class="Feature1_Text text-center" v-html="data.text"></p>
    <img
      v-if="data.image && data.image.src"
      :src="data.image.src"
      height="307"
      alt=""
      class="Feature1_Image d-block mx-auto object-fit-cover w-75"
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
