<script lang="ts">
  import type SpinnerTypes from "./spinner";
  export let color: SpinnerTypes["color"] = "#FF3E00";
  export let unit: SpinnerTypes["unit"] = "px";
  export let duration: SpinnerTypes["duration"] = "3s";
  export let size: SpinnerTypes["size"] = "60";
</script>

<style>
  .square {
    height: var(--size);
    width: var(--size);
    background-color: var(--color);
    animation: squareDelay var(--duration) 0s infinite
      cubic-bezier(0.09, 0.57, 0.49, 0.9);
    animation-fill-mode: both;
    perspective: 100px;
    display: inline-block;
  }
  @keyframes squareDelay {
    25% {
      -webkit-transform: rotateX(180deg) rotateY(0);
      transform: rotateX(180deg) rotateY(0);
    }
    50% {
      -webkit-transform: rotateX(180deg) rotateY(180deg);
      transform: rotateX(180deg) rotateY(180deg);
    }
    75% {
      -webkit-transform: rotateX(0) rotateY(180deg);
      transform: rotateX(0) rotateY(180deg);
    }
    100% {
      -webkit-transform: rotateX(0) rotateY(0);
      transform: rotateX(0) rotateY(0);
    }
  }
</style>

<div
  class="square"
  style="--size: {size}{unit}; --color: {color}; --duration: {duration};" />
