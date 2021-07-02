<template>
  <svg viewBox="0 0 1274 754" fill="none" xmlns="http://www.w3.org/2000/svg">
    <g id="sunfigma 1">
      <g id="sunbody">
        <path
          id="Vector"
          d="M62.4028 749.792H1274"
          stroke="#EDEDED"
          stroke-miterlimit="10"
        />
        <path
          id="Vector_2"
          d="M656.983 237.831C646.606 237.831 636.313 238.251 626.132 239.009C623.327 239.233 620.523 239.486 617.718 239.766C559.204 245.604 502.707 264.321 452.278 294.575C401.85 324.828 358.739 365.869 326.039 414.754C293.339 463.639 271.859 519.156 263.14 577.323C254.422 635.491 258.68 694.867 275.61 751.195H1038.47C1056.36 691.685 1060.08 628.816 1049.36 567.608C1038.63 506.399 1013.74 448.548 976.686 398.672C939.628 348.796 891.425 308.277 835.925 280.35C780.425 252.423 719.166 237.863 657.039 237.831H656.983Z"
          fill="#EDEDED"
          stroke="black"
          stroke-width="2"
          stroke-miterlimit="10"
        />
      </g>
      <g id="eyes">
        <path
          id="Vector_8"
          d="M724.294 690.881C730.49 690.881 735.512 685.858 735.512 679.66C735.512 673.463 730.49 668.439 724.294 668.439C718.098 668.439 713.075 673.463 713.075 679.66C713.075 685.858 718.098 690.881 724.294 690.881Z"
          fill="black"
          stroke="black"
          stroke-width="2"
          stroke-miterlimit="10"
        />
        <path
          id="Vector_9"
          d="M837.881 681.063C837.881 684.039 836.699 686.893 834.595 688.998C832.491 691.102 829.638 692.284 826.663 692.284C820.464 692.284 815.444 685.86 815.444 679.66C815.444 673.461 820.464 669.842 826.663 669.842C829.638 669.842 832.491 671.024 834.595 673.129C836.699 675.233 837.881 678.087 837.881 681.063Z"
          fill="black"
          stroke="black"
          stroke-width="2"
          stroke-miterlimit="10"
        />
      </g>
    </g>
    <defs>
      <linearGradient
        id="paint0_linear"
        x1="363"
        y1="-78"
        x2="863"
        y2="1098"
        gradientUnits="userSpaceOnUse"
      >
        <stop stop-color="#FFDB00" />
        <stop offset="1" stop-color="#FFDB00" />
      </linearGradient>
    </defs>
  </svg>
</template>

<script>
export default {
  name: "manny-moon"
};
</script>

<style lang="scss" scoped>
svg {
  width: 250px;
  height: 200px;
  @include m-large {
    width: 400px;
    height: 200px;
  }
}
#eyes {
  animation: sun-eyes 2s ease infinite;
  transform-origin: center;
  animation-direction: alternate;
}
@keyframes sun-eyes {
  0%,
  50% {
    transform: translate(100px, 0);
  }
  50.1%,
  100% {
    transform: translate(-350px, 0);
  }
}
</style>
