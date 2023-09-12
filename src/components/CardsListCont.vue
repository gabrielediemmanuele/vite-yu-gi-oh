<script>
import axios from "axios";

// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      /*  title: "Hello world", */
    };
  },

  // components: {
  //   MyComponent,
  // },
  created() {
    axios
      .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
      .then((response) => {
        console.log(response.data.data);
      });
  },
};
</script>

<template></template>

<style lang="scss" scoped></style>
