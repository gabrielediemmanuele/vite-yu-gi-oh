<script>
import CardsListCont from "./components/CardsListCont.vue";
import AppHeader from "./components/AppHeader.vue";
export default {
  data() {
    return {
      /* title: "Hello world", */
      maxCard: 50,
    };
  },
  components: { CardsListCont, AppHeader },
};
</script>

<template>
  <div class="general-cont">
    <AppHeader></AppHeader>
    <CardsListCont :maxItems="maxCard"></CardsListCont>
  </div>
</template>

<style lang="scss">
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-image: url(./assets/yugioh-background.jpg);
  background-repeat: no-repeat;
  background-size: cover;
  background-position: center;
}
.general-cont {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
