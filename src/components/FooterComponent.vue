<script setup>
</script>

<template>
  <footer class="x-footer-component">
    <div class="logo"></div>

    <div class="copyright">
      <span>&copy; All rights reserved by </span>
      <span class="company">Marigold Foundation</span>
    </div>

    <div class="stats">
      <div class="group">
        <i class="icon fa-brands fa-youtube"></i>
        <span class="stat">750,000</span>
      </div>

      <div class="group">
        <i class="icon fa-brands fa-facebook"></i>
        <span class="stat">750,000</span>
      </div>

      <div class="group">
        <i class="icon fa-brands fa-twitter"></i>
        <span class="stat">750,000</span>
      </div>

      <div class="group">
        <i class="icon fa-brands fa-instagram"></i>
        <span class="stat">750,000</span>
      </div>
    </div>
  </footer>
</template>

<style>
.x-footer-component {
  align-items: center;
  background-color: var(--x-foreground-color);
  color: var(--x-background-color);
  display: flex;
  gap: 2.5rem;
  justify-content: space-between;
  padding: 1.5rem 2.5rem 6rem;
}

.x-footer-component > .logo {
  background-color: var(--x-background-color);
  border-radius: 0.75rem;
  height: 4.5rem;
  width: 15rem;
}

.x-footer-component > .copyright {
  color: var(--x-mute-color);
  font-size: 1.25rem;
  font-weight: 500;
}

.x-footer-component > .copyright > .company {
  color: var(--x-background-color);
}

.x-footer-component > .stats {
  display: flex;
  gap: 1.5rem;
}

.x-footer-component > .stats > .group {
  align-items: center;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.x-footer-component > .stats > .group > .icon {
  font-size: 1.5rem;
}

.x-footer-component > .stats > .group > .stat {
  font-weight: 500;
}
</style>
