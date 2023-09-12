<script>
import CardsListCont from "./components/CardsListCont.vue";
import AppHeader from "./components/AppHeader.vue";
export default {
  data() {
    return {
      /* title: "Hello world", */
    };
  },
  components: { CardsListCont, AppHeader },
};
</script>

<template>
  <div class="general-cont">
    <AppHeader></AppHeader>
    <CardsListCont></CardsListCont>
  </div>
</template>

<style lang="scss">
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: rgb(96, 96, 228);
}
.general-cont {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
