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
  width: calc(100% / 5 - 40px);
  margin: 8px 8px 8px 8px;
  padding: 10px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  text-align: center;

  &:hover {
    background-color: rgb(214, 248, 142);
  }

  .card-name {
    font-size: 15px;
    font-weight: bold;
    margin: 5px 5px;
  }

  img {
    width: 100%;
    background-color: rgb(230, 111, 111);
  }
}
</style>
