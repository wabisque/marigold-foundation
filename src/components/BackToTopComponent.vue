<script setup>
import { computed, onUnmounted, ref } from 'vue';

let _frameId;
let isVisible = ref(false);
let progress = ref(0);

let ref_circle = ref(null);

let dashArray = computed(() => {
  let circumference = 2 * Math.PI * 22;

  return `${progress.value * circumference} ${(1 - progress.value) * circumference}`;
});
let dashOffset = computed(() => 2 * Math.PI * 22 * 0.25);

function onClick() {
  document.documentElement.scrollTo({
    behavior: 'smooth',
    top: 0
  });
}

function frame() {
  isVisible.value = document.documentElement.scrollTop > 70;
  progress.value = document.documentElement.scrollTop / (document.documentElement.scrollHeight - document.documentElement.clientHeight);
  _frameId = requestAnimationFrame(frame);
}

frame();

onUnmounted(() => cancelAnimationFrame(_frameId));
</script>

<template>
  <button
    class="x-back-to-top-component"
    :class="{
      '_is-visible': isVisible
    }"
    :style="{
      '--dash-array': dashArray,
      '--dash-offset': dashOffset
    }"
    @click="onClick"
  >
    <svg
      class="border"
      viewBox="0 0 49 49"
    >
      <circle
        class="circle"
        cx="24.5"
        cy="24.5"
        r="22"
        ref="ref_circle"
      />
    </svg>

    <i class="icon fa-solid fa-arrow-up"></i>
  </button>
</template>

<style>
.x-back-to-top-component {
  background-color: var(--x-foreground-color);
  border: none;
  border-radius: 100vmax;
  bottom: 1.5rem;
  cursor: pointer;
  height: 3.5rem;
  position: fixed;
  right: 1.5rem;
  transition-property: background-color, opacity;
  width: 3.5rem;
}

.x-back-to-top-component > .border {
  fill: none;
  height: 100%;
  left: 0px;
  position: absolute;
  top: 0px;
  width: 100%;
}

.x-back-to-top-component > .border > .circle {
  stroke: var(--x-background-color);
  stroke-dasharray: var(--dash-array);
  stroke-dashoffset: var(--dash-offset);
  stroke-width: 3px;
}

.x-back-to-top-component > .icon {
  color: var(--x-background-color);
  font-size: 1.5rem;
}

.x-back-to-top-component:not(._is-visible) {
  pointer-events: none;
  opacity: 0;
}
</style>
