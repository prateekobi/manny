<template>
  <div class="wrapper" :class="{ 'is-night': is_night }">
    <div
      class="container-fluid page-wrapper px-0 d-flex justify-content-center"
    >
      <div class="container align-self-center">
        <div class="row mx-n1">
          <div class="col-12 px-1 text-center">
            <p class="title">
              Good {{ is_night ? "night" : "morning" }} Manny!
            </p>
            <p class="subtitle">from Prateek</p>
          </div>
          <div class="col-12 px-1 text-center mt-5">
            <manny-moon v-if="is_night"></manny-moon>
            <manny-sun v-else></manny-sun>
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
  },
  data() {
    return {
      is_night: false
    };
  },
  methods: {
    sortDate() {
      const now = new Date().getHours();
      const is_day = now > 6 && now < 20;

      if (!is_day) {
        this.is_night = true;
      }
    }
  },
  mounted() {
    this.sortDate();
  }
};
</script>

<style lang="scss" scoped>
.wrapper {
  background-color: #cd113b;
  &.is-night {
    background-color: #171717;
    .title {
      color: #185adb;
      font-size: 20px;
    }

    .subtitle {
      color: #ffc947;
    }
  }

  .title {
    color: #ffa900;
    font-size: 20px;
  }

  .page-wrapper {
    height: 100vh;
  }
}
</style>
