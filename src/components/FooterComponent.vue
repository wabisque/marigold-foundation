<script setup>
import HorizontalLogoComponent from '@/components/HorizontalLogoComponent.vue';
</script>

<template>
  <footer class="x-footer-component">
    <horizontal-logo-component class="logo"/>

    <div class="copyright">
      <span>&copy; All rights reserved by </span>
      <span class="company">Marigold Hope Foundation</span>
    </div>

    <div class="stats">
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
  background-color: var(--x-foreground-color);
  color: var(--x-background-color);
  display: grid;
  gap: 2.5rem;
  grid-template-columns: [ copyright-start logo-start stats-start ] 1fr [ copyright-end logo-end stats-end ];
  grid-template-rows: [ logo-start ] auto [ logo-end stats-start ] auto [ stats-end copyright-start ] auto [ copyright-end ];
  padding: 2.5rem 1.5rem 6rem;
}

.x-footer-component > .logo {
  width: 13.5rem;
  grid-area: logo;
}

.x-footer-component > .copyright {
  color: var(--x-mute-color);
  font-size: 1.25rem;
  grid-area: copyright;
  text-align: center;
}

.x-footer-component > .copyright > .company {
  color: var(--x-background-color);
  font-weight: 500;
}

.x-footer-component > .stats {
  display: flex;
  gap: 1.5rem;
  grid-area: stats;
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

@media screen and (min-width: 768px) {
  .x-footer-component {
    grid-template-columns: [ copyright-start logo-start ] auto [ logo-end stats-start ] 1fr [ copyright-end stats-end ];
    grid-template-rows: [ logo-start stats-start ] auto [ logo-end stats-end copyright-start ] auto [ copyright-end ];
    justify-items: initial;
  }

  .x-footer-component > .stats {
    justify-content: end;
  }
}

@media screen and (min-width: 992px) {
  .x-footer-component {
    grid-template-columns: [ logo-start ] auto [ logo-end copyright-start ] 1fr [ copyright-end stats-start ] auto [ stats-end ];
    grid-template-rows: [ copyright-start logo-start stats-start ] auto [ copyright-end logo-end stats-end ];
    justify-items: initial;
  }

  .x-footer-component > .stats {
    justify-content: end;
  }
}

@media screen and (min-width: 1200px) {
  .x-footer-component {
    padding: 2.5rem 2.5rem 6rem;
  }
}
</style>
