<!--
  Usage:
```md
---
```yaml
layout: three-cols-header
```

This spans both

::left::
# Left
This shows on the left

::center::
# Center
This shows on the center

::right::
# Right
This shows on the right

::bottom::
This shows at the bottom, aligned to the end (bottom) of the grid
```
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
  <section class="slidev-layout three-cols-header" :class="layoutClass">
    <div class="col-header">
      <slot />
    </div>
    <div class="cols">
      <div class="col-left" :class="props.class">
        <slot name="left" />
      </div>
      <div class="col-center" :class="props.class">
        <slot name="center" />
      </div>
      <div class="col-right" :class="props.class">
        <slot name="right" />
      </div>
    </div>
    <slides-current-number />
  </section>
</template>

<style>
.slidev-layout.three-cols-header {
  padding: 5rem 8rem 6rem;

  h3 {
    font-size: 3rem;
    line-height: 3.5rem;
    margin-bottom: 40px;
    transform: translate(-70px);
    width: 850%;
  }

  h4 {
    font-family: var(--font-primary);
  }

  .cols {
    display: grid;
    grid-column-gap: 20px;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: 1fr;
  }

  .col {
    &-left {
      grid-area: 1 / 1 / 2 / 2;
    }

    &-center {
      grid-area: 1 / 2 / 2 / 3;
    }

    &-right {
      grid-area: 1 / 3 / 2 / 4;
    }
  }
}
</style>
