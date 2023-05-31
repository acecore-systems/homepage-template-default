<template>
  <section class="container my-5 ">
    <div class="row mx-lg-5 mx-3">
      <div class="col-6 d-flex align-items-center p-4">
        <div>
          <p v-if="data.shoulderCopy" class="text-muted">{{ data.shoulderCopy }}</p>
          <h2 v-if="data.titleCopy">{{ data.titleCopy }}</h2>
          <p v-if="data.text">{{ data.text }}</p>
          <a v-if="data.ctaButton && data.ctaButton.label" class="btn btn-outline-primary" :href="data.ctaButton.url"
            rel="noreferrer noopener" :target="data.ctaButton.newTab ? '_blank' : ''">{{ data.ctaButton.label }}</a>
        </div>
      </div>
      <div v-if="data.backgroundImage" class="col-lg-6 p-0">
        <img :src="data.backgroundImage.src" class="img-fluid rounded-4 w-100 h-auto" alt="" />
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
          shoulderCopy: '',
          titleCopy: '',
          text: '',
          ctaButton: {
            label: '',
            url: '',
            newTab: false,
          },
        }
      },
    },
  },
}
</script>