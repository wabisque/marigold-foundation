<script setup>
import HorizontalLogoComponent from '@/components/HorizontalLogoComponent.vue';

const emit = defineEmits([
  'info'
]);
</script>

<template>
  <header class="x-header-component">
    <horizontal-logo-component class="logo"/>

    <button
      class="info"
      @click="emit('info', $event)"
    >
      <i class="icon fa-solid fa-info"></i>
    </button>
  </header>
</template>

<style>
.x-header-component {
  align-items: center;
  border-bottom: 1px solid var(--x-foreground-color);
  display: flex;
  gap: 1.5rem;
  height: 7.5rem;
  justify-content: space-between;
  padding: 0px 1.5rem;
  width: 100%;
}

.x-header-component > .logo {
  width: 13.5rem;
}

.x-header-component > .info {
  background-color: transparent;
  border: none;
  border-radius: 0.75rem;
  cursor: pointer;
  padding: 0.75rem 0.875rem;
}

.x-header-component > .info > .icon {
  font-size: 1.5rem;
  width: 1.5rem;
}

.x-header-component > .info:hover {
  background-color: var(--x-surface-color);
}

.x-header-component > .info:hover > .icon {
  color: var(--x-primary-color);
}

@media screen and (min-width: 1200px) {
  .x-header-component {
    padding: 0px 2.5rem;
  }
}
</style>
