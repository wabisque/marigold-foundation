<script setup>
import { computed, ref } from 'vue';

let isOpened = ref(false);

function close() {
  isOpened.value = false;
}

function open() {
  isOpened.value = true;
}

defineExpose({
  close,
  isOpened: computed(() => isOpened.value),
  open
});
</script>

<template>
  <section
    class="x-info-panel-component"
    :class="{
      '_is-opened': isOpened
    }"
    @click="
      if($event.target.matches('.x-info-panel-component')) close();
    "
  >
    <aside class="aside">
      <header class="header">
        <h1 class="title">Info</h1>

        <button
          class="close"
          @click="close"
        >
          <i class="icon fa-solid fa-close"></i>
        </button>
      </header>
      
      <main class="main">
        <div class="follow">
          <div class="label">Follow</div>
  
          <div class="actions">
            <a
              class="action"
              href="javascript:void(0);"
            >
              <i class="icon fa-brands fa-facebook"></i>
            </a>

            <a
              class="action"
              href="javascript:void(0);"
            >
              <i class="icon fa-brands fa-twitter"></i>
            </a>

            <a
              class="action"
              href="javascript:void(0);"
            >
              <i class="icon fa-brands fa-instagram"></i>
            </a>
          </div>
        </div>
      </main>
    </aside>
  </section>
</template>

<style>
.x-info-panel-component {
  background-color: var(--x-shadow-color);
  height: 100vh;
  position: fixed;
  width: 100vw;
}

.x-info-panel-component > .aside {
  background-color: var(--x-surface-color);
  display: grid;
  grid-template-columns: [ header-start main-start ] 1fr [ header-end main-end ];
  grid-template-rows: [ header-start ] auto [ header-end main-start ] 1fr [ main-end ];
  height: 100%;
  margin-left: auto;
  transition-property: translate;
  width: min(27.5rem, 100%);
}

.x-info-panel-component > .aside > .header {
  align-items: center;
  border-bottom: 1px solid var(--x-mute-color);
  display: flex;
  grid-area: header;
  height: calc(7.5rem + 1px);
  justify-content: space-between;
  padding: 0px 1.5rem;
}

.x-info-panel-component > .aside > .header > .title {
  font-size: 2.5rem;
  margin: 0;
}

.x-info-panel-component > .aside > .header > .close {
  background-color: transparent;
  border: none;
  border-radius: 0.75rem;
  cursor: pointer;
  padding: 0.75rem 0.875rem;
}

.x-info-panel-component > .aside > .header > .close > .icon {
  font-size: 1.5rem;
  width: 1.5rem;
}

.x-info-panel-component > .aside > .header > .close:hover {
  background-color: var(--x-background-color);
}

.x-info-panel-component > .aside > .header > .close:hover > .icon {
  color: var(--x-primary-color);
}

.x-info-panel-component > .aside > .main {
  grid-area: main;
  overflow: hidden auto;
}

.x-info-panel-component > .aside > .main > .follow {
  align-items: center;
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  padding: 1.5rem;
}

.x-info-panel-component > .aside > .main > .follow > .label {
  font-size: 1.125rem;
  font-weight: 500;
}

.x-info-panel-component > .aside > .main > .follow > .actions {
  align-items: center;
  display: flex;
  gap: 1.5rem;
  justify-content: center;
}

.x-info-panel-component > .aside > .main > .follow > .actions > .action > .icon {
  font-size: 1.75rem;
}

.x-info-panel-component > .aside > .main > .follow > .actions > .action:hover > .icon {
  color: var(--x-primary-color);
}

.x-info-panel-component:not(._is-opened) {
  background-color: transparent;
  pointer-events: none;
}

.x-info-panel-component:not(._is-opened) > .aside {
  translate: 100% 0px;
}
</style>
