<script>
import axios from "axios";

// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      yugiohCards: [],
    };
  },

  // components: {
  //   MyComponent,
  // },
  methods: {
    catchCards() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then((response) => {
          console.log(response.data.data);
          this.yugiohCards = response.data.data;
        });
    },
  },
  created() {
    this.catchCards();
  },
};
</script>

<template>
  <section class="cards-cont">
    <div class="card" v-for="card in yugiohCards" :key="card.id">
      <img :src="card.card_images.image_url" alt="" />
      <span>{{ card.name }}</span>
      <span>{{ card.archetype }}</span>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.card {
  width: 100px;
  height: 300px;

  img {
    width: 100%;
  }
}
</style>
