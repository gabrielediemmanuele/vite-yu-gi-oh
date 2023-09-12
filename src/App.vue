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

<style lang="scss" scoped>
.general-cont {
  background-color: rgb(96, 96, 228);
  font-family: Arial, Helvetica, sans-serif;
}
</style>
