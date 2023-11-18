<script setup>
</script>

<template>
  <header class="x-header-component">
    <div class="logo-wrapper">
      <div class="logo"></div>
    </div>

    <button class="info">
      <i class="icon fa-solid fa-bars"></i>
    </button>
  </header>
</template>

<style>
.x-header-component {
  align-items: center;
  border-bottom: 1px solid var(--x-foreground-color);
  display: flex;
  gap: 2.5rem;
  justify-content: space-between;
  padding: 0px 2.5rem;
}

.x-header-component > .logo-wrapper {
  border-right: 1px solid var(--x-foreground-color);
  padding: 1.5rem 2.5rem 1.5rem 0px;
}

.x-header-component > .logo-wrapper > .logo {
  background-color: var(--x-foreground-color);
  border-radius: 0.75rem;
  height: 4.5rem;
  width: 15rem;
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
}

.x-header-component > .info:hover {
  background-color: var(--x-foreground-color);
}

.x-header-component > .info:hover > .icon {
  color: var(--x-background-color);
}
</style>
