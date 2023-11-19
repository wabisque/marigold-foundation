<script setup>
import { ref } from 'vue';

let props = defineProps({
  itemsLength: {
    default: 1,
    type: Number
  }
});

let current = ref(1);
</script>

<template>
  <div class="x-carousel-component">
    <button class="action previous">
      <svg
        class="icon"
        viewBox="0 0 24 24"
        fill="none"
      >
        <path fill-rule="evenodd" clip-rule="evenodd" d="M13.8128 21.7458C13.539 22.0566 13.0651 22.0866 12.7543 21.8128L2.25426 12.5628C2.02015 12.3565 1.93817 12.0269 2.0484 11.735C2.15863 11.4431 2.43804 11.25 2.75003 11.25L21.25 11.25C21.6642 11.25 22 11.5858 22 12C22 12.4142 21.6642 12.75 21.25 12.75L4.73598 12.75L13.7458 20.6872C14.0566 20.961 14.0866 21.435 13.8128 21.7458Z"/>
      </svg>
    </button>

    <div class="current">
      <template v-for="number of props.itemsLength">
        <slot
          :name="`item-${number}`"
          v-if="number == current"
        ></slot>
      </template>
    </div>

    <button class="action next">
      <svg
        class="icon"
        viewBox="0 0 24 24"
        fill="none"
      >
        <path fill-rule="evenodd" clip-rule="evenodd" d="M10.1872 2.25423C10.461 1.94342 10.935 1.91342 11.2458 2.18723L21.7458 11.4372C21.9799 11.6435 22.0619 11.9731 21.9516 12.265C21.8414 12.5569 21.562 12.75 21.25 12.75H2.75C2.33579 12.75 2 12.4142 2 12C2 11.5858 2.33579 11.25 2.75 11.25H19.2641L10.2542 3.31277C9.94342 3.03896 9.91342 2.56504 10.1872 2.25423Z"/>
      </svg>
    </button>

    <div class="indicator">
      <span class="current">{{ current }}</span>
      <div class="dash"></div>
      <span class="total">{{ props.itemsLength }}</span>
    </div>
  </div>
</template>

<style>
.x-carousel-component {
  display: grid;
  grid-template-columns: [ indicator-start previous-start ] auto [ previous-end current-start ] 1fr [ current-end next-start ] auto [ indicator-end next-end ];
  grid-template-rows: [ current-start next-start previous-start ] 1fr [ current-end next-end previous-end indicator-start ] auto [ indicator-end ];
  gap: 2.5rem;
}

.x-carousel-component > .action {
  align-self: center;
  background-color: transparent;
  border: none;
  border-radius: 0.75rem;
  cursor: pointer;
  padding: 0.75rem 0.875rem;
}

.x-carousel-component > .action > .icon {
  display: block;
  fill: var(--x-foreground-color);
  font-size: 1.5rem;
  width: 1.5rem;
}

.x-carousel-component > .action:hover {
  background-color: var(--x-surface-color);
}

.x-carousel-component > .action:hover > .icon {
  fill: var(--x-primary-color);
}

.x-carousel-component > .previous {
  grid-area: previous;
}

.x-carousel-component > .next {
  grid-area: next;
}

.x-carousel-component > .indicator {
  align-items: center;
  display: flex;
  gap: 0.5rem;
  grid-area: indicator;
  justify-content: center;
}

.x-carousel-component > .indicator > .current {
  font-weight: 500;
}

.x-carousel-component > .indicator > .dash {
  border-bottom: 1px solid var(--x-foreground-color);
  width: min(50%, 15rem);
}

.x-carousel-component > .indicator > .total {
  color: var(--x-mute-color);
  font-weight: 300;
}
</style>
