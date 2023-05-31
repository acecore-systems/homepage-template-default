<template>
  <section class="my-5">
    <div class="row">
    <div class="d-flex bd-highlight">
      <div class="col-6 bd-highlight">
        <h3
          v-if="data.titleCopy"
          v-html="data.titleCopy"
        ></h3>
        <p v-if="data.text" v-html="data.text"></p>
      </div>   
      <div v-if="data.image && data.image.src" class="col-6 bd-highlight">
        <img :src="data.image.src" alt="" class="img-fluid w-100"/>
      </div>
    </div>
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
