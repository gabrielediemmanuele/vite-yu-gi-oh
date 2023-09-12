<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      /*  title: "Hello world" */
    };
  },
  props: {
    yugiCard: Object[String],
  },

  // components: {
  //   MyComponent,
  // },
};
</script>

<template>
  <div class="card">
    <img :src="yugiCard.card_images[0].image_url" alt="" />
    <span class="card-name">{{ yugiCard.name }}</span>
    <span class="card-archetype">{{ yugiCard.archetype }}</span>
  </div>
</template>

<style lang="scss">
.card {
  width: calc(100% / 6 - 30px);
  margin: 15px 8px 25px 8px;
  height: 325px;
  padding: 5px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  text-align: center;

  .card-name {
    font-size: 15px;
    font-weight: bold;
    margin: 5px 5px;
  }
  .card-archetype {
  }
  img {
    width: 100%;
    background-color: rgb(230, 111, 111);
  }
}
</style>
