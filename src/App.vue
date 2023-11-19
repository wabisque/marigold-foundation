<script setup>
import { ref, watch } from 'vue';

import BackToTopComponent from '@/components/BackToTopComponent.vue';
import FooterComponent from '@/components/FooterComponent.vue';
import HeaderComponent from '@/components/HeaderComponent.vue';
import InfoPanelComponent from '@/components/InfoPanelComponent.vue';

let ref_infoPanel = ref(null);

watch(
  () => ref_infoPanel.value?.isOpened ?? false,
  value => document.documentElement.style.overflowY = value ? 'hidden' : 'auto'
);
</script>

<template>
  <header-component
    class="header"
    @info="ref_infoPanel?.open()"
  />

  <router-view class="main"/>
  
  <footer-component class="footer"/>

  <back-to-top-component/>

  <info-panel-component ref="ref_infoPanel"/>
</template>

<style>
#app {
  display: grid;
  grid-template-columns: [ footer-start header-start main-start] 100% [ footer-end header-end main-end];
  grid-template-rows: [ header-start] auto [ header-end main-start] 1fr [ main-end footer-start] auto [ footer-end];
  min-height: 100vh;
  width: 100%;
}

#app > .header {
  grid-area: header;
}

#app > .main {
  grid-area: main;
}

#app > .footer {
  grid-area: footer;
}
</style>
