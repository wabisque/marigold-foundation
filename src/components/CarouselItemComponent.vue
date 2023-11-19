<script setup>
</script>

<template>
  <div class="x-carousel-item-component">
    <div class="image">
      <slot name="image"></slot>
    </div>

    <div class="content">
      <slot></slot>
    </div>
  </div>
</template>

<style>
.x-carousel-item-component {
  display: grid;
  grid-template-columns: [ content-start image-start ] 1fr [ content-end image-end ];
  grid-template-rows: [ image-start ] 2fr [ content-start ] 1fr [ image-end ] 2fr [ content-end ];
  width: 100%;
}

.x-carousel-item-component > .image {
  aspect-ratio: 1;
  border-radius: 100vmax;
  grid-area: image;
  overflow: hidden;
  width: 100%;
}

.x-carousel-item-component > .image > img {
  height: 100%;
  object-fit: cover;
  object-position: center;
  width: 100%;
}

.x-carousel-item-component > .content {
  aspect-ratio: 1;
  background-color: var(--x-foreground-color);
  border-radius: 100vmax;
  color: var(--x-background-color);
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  grid-area: content;
  justify-content: center;
  overflow: hidden;
  padding: 2.5rem;
  width: 100%;
}

.x-carousel-item-component > .content > .place-time {
  color: var(--x-mute-color);
  font-weight: 500;
  text-align: center;
}

.x-carousel-item-component > .content > .title {
  font-size: 1.25rem;
  font-weight: 500;
  text-align: center;
}

.x-carousel-item-component > .content > .description {
  color: var(--x-mute-color);
  font-weight: 300;
  text-align: center;
}
</style>
