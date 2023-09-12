<script>
import axios from "axios";
import Card from "./Card.vue";

// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      yugiohCards: [],
    };
  },

  components: {
    Card,
  },
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
    <Card v-for="card in yugiohCards" :key="card.id" :yugiCard="card"> </Card>
  </section>
</template>

<style lang="scss">
.cards-cont {
  width: 80%;
  margin: 30px auto;
  background-color: white;
  display: flex;
  flex-wrap: wrap;
  padding: 50px 35px;
  border-radius: 20px;
  align-items: center;
  justify-content: center;
}
</style>
