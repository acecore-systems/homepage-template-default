<template>
  <section class="Logos">
    <h3 v-if="data.text" class="Logos_Title" v-html="data.text"></h3>
    <ul class="Logos_List">
      <li v-for="logo in data.logoImages" :key="logo._id">
        <img :src="logo.src" alt="" />
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: {
    data: {
      type: Object,
      default() {
        return {
          text: '',
          logoImages: [],
        }
      },
    },
  },
}
</script>

<style>
.Logos_List{
  list-style: none;
  padding-left: 5px;
  display: flex;
  flex-wrap: wrap;
	justify-content: center;
}
.Logos_List li{
  margin-right: 1vw;

}
.Logos_List li img{
  width:13vw ;
  height: auto;
}
</style>
