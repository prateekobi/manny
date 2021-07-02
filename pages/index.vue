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
            <!-- <manny-sun></manny-sun> -->
            <manny-moon></manny-moon>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MannySun from "@/components/MannySun";
import MannyMoon from "@/components/MannyMoon";

export default {
  name: "home-page",
  components: {
    MannySun,
    MannyMoon
  }
};
</script>

<style lang="scss" scoped>
.wrapper {
  background-color: #171717;
  .title {
    color: #ffa900;
    font-size: 20px;
  }
  .sun-container {
    height: 100vh;
  }
}
</style>
