<script>
import CardsListCont from "./components/CardsListCont.vue";
export default {
  data() {
    return {
      title: "Hello world",
    };
  },
  components: { CardsListCont },
};
</script>

<template>
  <h1>{{ title }}</h1>
  <CardsListCont></CardsListCont>
</template>

<style lang="scss" scoped></style>
