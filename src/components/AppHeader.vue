<script>
export default {
  data() {
    return {};
  },
};
</script>

<template>
  <header>
    <div class="container">
      <img src="../../src/assets/pngegg.png" alt="" />
      <span>API</span>
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
  background-color: rgba(0, 0, 0, 0.7);
  margin-bottom: 20px;
  img {
    height: 100px;
  }
  span {
    font-size: 50px;
    color: white;
  }
}
</style>
