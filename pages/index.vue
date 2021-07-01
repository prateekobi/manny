<template>
  <div class="wrapper">
    <div
      class="container-fluid sun-container px-0 d-flex justify-content-center"
    >
      <div class="container align-self-center">
        <div class="row mx-n1">
          <div class="col-12 px-1 text-center">
            <p class="title">Good morning Manny!</p>
            <p class="subtitle">from Prateek</p>
          </div>
          <div class="col-12 px-1 text-center mt-5">
            <manny-sun></manny-sun>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MannySun from "@/components/MannySun";

export default {
  name: "home-page",
  components: {
    MannySun
  }
};
</script>

<style lang="scss" scoped>
.wrapper {
  .title {
    color: #ffa900;
    font-size: 20px;
  }
  .sun-container {
    height: 100vh;
  }
}
</style>
