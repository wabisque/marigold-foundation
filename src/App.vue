<script setup>
import BackToTopComponent from '@/components/BackToTopComponent.vue';
import FooterComponent from '@/components/FooterComponent.vue';
import HeaderComponent from '@/components/HeaderComponent.vue';
</script>

<template>
  <header-component class="header"/>

  <router-view class="main"/>
  
  <footer-component class="footer"/>

  <back-to-top-component/>
</template>

<style>
#app {
  display: grid;
  grid-template-columns: [ footer-start header-start main-start] 1fr [ footer-end header-end main-end];
  grid-template-rows: [ header-start] auto [ header-end main-start] 1fr [ main-end footer-start] auto [ footer-end];
  min-height: 100vh;
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
