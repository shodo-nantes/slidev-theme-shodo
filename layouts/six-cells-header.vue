<!--
  Usage:
```md
---
```yaml
layout: six-cells-header
```

This spans both

::top-left::
#### Top left
This shows on the top left

::top-center::
#### Top center
This shows on the top center

::top-right::
#### Top right
This shows on the top right

::bottom-left::
#### Bottom left
This shows on the bottom left

::bottom-center::
#### Bottom center
This shows on the bottom center

::bottom-right::
# Bottom right
This shows on the bottom right
-->

<script setup lang="ts">
const props = defineProps({
  class: {
    type: String,
  },
  layoutClass: {
    type: String,
  },
});
</script>

<template>
  <section class="slidev-layout six-cells-header" :class="layoutClass">
    <div class="col-header">
      <slot />
    </div>
    <div class="cells">
      <div class="col-top-left" :class="props.class">
        <slot name="top-left" />
      </div>
      <div class="col-top-center" :class="props.class">
        <slot name="top-center" />
      </div>
      <div class="col-top-right" :class="props.class">
        <slot name="top-right" />
      </div>
      <div class="col-bottom-left" :class="props.class">
        <slot name="bottom-left" />
      </div>
      <div class="col-bottom-center" :class="props.class">
        <slot name="bottom-center" />
      </div>
      <div class="col-bottom-right" :class="props.class">
        <slot name="bottom-right" />
      </div>
    </div>
    <slides-current-number />
  </section>
</template>

<style>
.slidev-layout.six-cells-header {
  padding: 5rem 8rem 6rem;

  h3 {
    font-size: 3rem;
    line-height: 3.5rem;
    margin-bottom: 50px;
    transform: translate(-70px);
    width: 850%;
  }

  h4 {
    font-family: var(--font-primary);
  }

  .cells {
    display: grid;
    grid-column-gap: 20px;
    grid-row-gap: 20px;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 1fr);

    &-top-left {
      grid-area: 1 / 1 / 2 / 2;
    }

    &-top-center {
      grid-area: 1 / 1 / 2 / 2;
    }

    &-top-right {
      grid-area: 1 / 3 / 2 / 4;
    }

    &-bottom-left {
      grid-area: 2 / 1 / 3 / 2;
    }

    &-bottom-center {
      grid-area: 2 / 2 / 3 / 3;
    }

    &-bottom-right {
      grid-area: 2 / 3 / 3 / 4;
    }
  }
}
</style>
