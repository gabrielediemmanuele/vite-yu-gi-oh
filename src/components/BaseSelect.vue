<script>
/* import { store } from "../data/store"; */
import axios from "axios";
export default {
  data() {
    return {
      archetypes: [],
      filter: "",
      /* store, */
    };
  },

  props: {
    placeholder: String,
  },

  methods: {
    filterCard() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
        .then((response) => {
          /* console.log(response.data); */
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
    <select
      name="card-type"
      id="card-type"
      v-model="filter"
      @change="$emit('search', filter)"
    >
      <option value="" :placeholder="placeholder">Scegli un archetipo</option>
      <option v-for="archetype in archetypes" :value="archetype.archetype_name">
        {{ archetype.archetype_name }}
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
