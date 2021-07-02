<template>
  <div class="wrapper" :class="{ 'is-night': is_night }">
    <div
      class="container-fluid page-wrapper px-0 d-flex justify-content-center"
    >
      <div v-if="is_night">
        <div id="stars-group-1"></div>
        <div id="stars-group-2"></div>
        <div id="stars-group-3"></div>
        <div id="stars-group-4"></div>
        <div id="stars-group-5"></div>
        <div id="stars-group-6"></div>
      </div>
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
    background-color: #000;
    .title {
      color: #fff;
      font-size: 20px;
    }

    .subtitle {
      color: #185adb;
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

@function generate-random-stars($screen-width, $color, $density) {
  $h-shadow: random($screen-width);
  $v-shadow: random($screen-width);

  $stars: "#{$h-shadow}px #{$v-shadow}px #{$color}";
  @for $i from 2 through $density {
    $h-shadow: random($screen-width);
    $v-shadow: random($screen-width);

    $stars: "#{$stars}, #{$h-shadow}px #{$v-shadow}px #{$color}";
  }
  @return unquote($stars);
}

@mixin stars-content($screen-width, $color, $density, $speed, $delay) {
  width: 2px;
  height: 2px;
  border-radius: 50%;
  opacity: 0;
  box-shadow: generate-random-stars($screen-width, $color, $density);
  animation-name: glowing-stars;
  animation-duration: $speed + s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
  animation-timing-function: linear;
  animation-delay: $delay + s;
}

body {
  background: #000;
}

//Change colors for multi-colors star groups

#stars-group-1 {
  @include stars-content(1800, #fff, 200, 1, 0);
}

#stars-group-2 {
  @include stars-content(1800, #fff, 200, 1, 0.1);
}

#stars-group-3 {
  @include stars-content(1800, #fff, 200, 1, 0.2);
}

#stars-group-4 {
  @include stars-content(1800, #fff, 200, 1, 0.3);
}

#stars-group-5 {
  @include stars-content(1800, #fff, 200, 1, 0.4);
}

#stars-group-6 {
  @include stars-content(1800, #fff, 200, 1, 0.5);
}

@keyframes glowing-stars {
  0% {
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    opacity: 0;
  }
}
</style>
