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
      store,
    };
  },
  //Component card.vue
  components: {
    Card,
    BaseSelect,
  },
  props: {
    maxItems: Number,
  },

  // Axios for remote array of cards
  methods: {
    //FILTER
    getSearch(filter) {
      let results = `https://db.ygoprodeck.com/api/v7/cardinfo.php?num=${this.maxItems}&offset=0`;
      if (filter) {
        results += `&archetype=${filter}`;
      }
      axios.get(results).then((response) => {
        this.store.yugiohCards = response.data.data;
      });
    },
  },
  created() {
    this.getSearch("");
  },
};
</script>

<template>
  <!--   Add a select like in the screenshot  -->
  <BaseSelect placeholder="Search Archetype" @search="getSearch"></BaseSelect>
  <!--   CARD COUNTER  -->
  <div class="card-counter-bar">
    {{ "Numero di carte trovate: " + store.yugiohCards.length }}
  </div>

  <!--   CARD CONTAINER  -->
  <section class="cards-cont">
    <Card v-for="card in store.yugiohCards" :key="card.id" :yugiCard="card">
    </Card>
  </section>
</template>

<style lang="scss">
.card-counter-bar {
  background-color: rgba(255, 255, 255, 0.8);
  width: 80%;
  margin: 30px auto;
  padding: 10px;
  border-radius: 10px;
}
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
