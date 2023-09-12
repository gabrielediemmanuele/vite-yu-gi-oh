<script>
//Axios
import axios from "axios";
//Component card.vue
import Card from "./Card.vue";

export default {
  data() {
    return {
      yugiohCards: [],
    };
  },
  //Component card.vue
  components: {
    Card,
  },

  // Axios for remote array of cards
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
  <!--   Add a select like in the screenshot  -->
  <div>
    <select name="card-type" id="card-type">
      <option value="Alien">Alien</option>
      <option value="Noble Knight">Noble Knight</option>
      <option value="Melodious">Melodious</option>
      <option value="Tainted Treasure">Tainted Treasure</option>
    </select>
  </div>
  <section class="cards-cont">
    <Card v-for="card in yugiohCards" :key="card.id" :yugiCard="card"> </Card>
  </section>
</template>

<style lang="scss">
.cards-cont {
  width: 80%;
  margin: 30px auto;
  background-color: rgba(255, 255, 255, 0.8);
  display: flex;
  flex-wrap: wrap;
  padding: 20px 20px;
  border-radius: 20px;
  justify-content: center;
}

//* select options
div > #card-type {
  margin: 0 200px;
  padding: 10px;
  font-size: 20px;
  border-radius: 12px;
}
</style>
