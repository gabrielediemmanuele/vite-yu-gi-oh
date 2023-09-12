<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      /*  title: "Hello world" */
    };
  },
  props: {
    yugiCard: String,
  },

  // components: {
  //   MyComponent,
  // },
};
</script>

<template>
  <div class="card">
    <img :src="yugiCard.card_images[0].image_url" alt="" />
    <span>{{ yugiCard.name }}</span>
    <span>{{ yugiCard.archetype }}</span>
  </div>
</template>

<style lang="scss" scoped>
.card {
  width: calc(100% / 5 - 30px);
  margin: 5px 5px 5px 5px;
  height: 320px;

  img {
    width: 100%;
    background-color: rgb(230, 111, 111);
  }
}
</style>
