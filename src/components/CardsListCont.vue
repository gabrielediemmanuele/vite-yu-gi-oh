<script>
//Axios
import axios from "axios";
//Component card.vue
import Card from "./Card.vue";
import BaseSelect from "./BaseSelect.vue";

import { store } from "../data/store";

export default {
  data() {
    return {
      cardsUrl: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0",
      store,
    };
  },
  //Component card.vue
  components: {
    Card,
    BaseSelect,
  },

  // Axios for remote array of cards
  methods: {
    catchCards() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=100&offset=0")
        .then((response) => {
          /* console.log(response.data.data); */
          this.store.yugiohCards = response.data.data;
        });
    },
    //FILTER
    getSearch(filter) {
      const results = `${this.cardsUrl}&archetypes=${filter}`;
      this.catchCards(results);
    },
  },
  created() {
    this.catchCards();
  },
};
</script>

<template>
  <!--   Add a select like in the screenshot  -->
  <BaseSelect placeholder="Search Archetype" @search="getSearch"></BaseSelect>
  <section class="cards-cont">
    <Card v-for="card in store.yugiohCards" :key="card.id" :yugiCard="card">
    </Card>
  </section>
</template>

<style lang="scss">
.cards-cont {
  width: 80%;
  margin: 30px auto;
  height: 600px;
  background-color: rgba(255, 255, 255, 0.8);
  display: flex;
  flex-wrap: wrap;
  padding: 20px 20px;
  border-radius: 20px;
  justify-content: center;
  overflow-y: auto;
}
</style>
