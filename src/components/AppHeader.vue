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
      <span>.API</span>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
  img {
    height: 100%;
  }
  span {
    margin-left: 20px;
    font-size: 50px;
  }
}
</style>
