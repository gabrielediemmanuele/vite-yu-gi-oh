<script>
/* import { store } from "../data/store"; */
import axios from "axios";
export default {
  data() {
    return {
      archetypes: "",
      /* store, */
    };
  },
  methods: {
    filterCard() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
        .then((response) => {
          console.log(response);
          this.archetypes = response.data;
        });
    },
  },
  created() {
    this.filterCard();
  },

  // components: {
  //   MyComponent,
  // },
};
</script>

<template>
  <div>
    <select name="card-type" id="card-type" v-model="type">
      <option value="scegli valore" placeholder="scegli un archetipo">
        Scegli un archetipo
      </option>
      <option v-for="archetype in archetypes" :value="archetype">
        {{ archetype }}
      </option>
    </select>
  </div>
</template>

<style lang="scss" scoped>
//* select options
div > #card-type {
  margin: 0 200px;
  padding: 10px;
  font-size: 20px;
  border-radius: 12px;
}
</style>
