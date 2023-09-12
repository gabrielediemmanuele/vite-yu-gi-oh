<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {};
  },

  // components: {
  //   MyComponent,
  // },
};
</script>

<template>
  <header>
    <div class="container">
      <img src="../../src/assets/pngegg.png" alt="" />
      <span>YU-GI-OH! API</span>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 200px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  img {
    height: 100px;
  }
  span {
    font-size: 50px;
    color: white;
  }
}
</style>
