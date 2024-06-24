<!--
  Usage:
```md
---
layout: two-cols-header
---

This spans both

::left::
# Left
This shows on the left

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
  <div class="slidev-layout two-cols-header" :class="layoutClass">
    <div class="col-header">
      <slot />
    </div>
    <div class="cols">
      <div class="col-left" :class="props.class">
        <slot name="left" />
      </div>
      <div class="col-right" :class="props.class">
        <slot name="right" />
      </div>
      <div class="col-bottom" :class="props.class">
        <slot name="bottom" />
      </div>
    </div>
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.two-cols-header {
  padding: 5rem 8rem 6rem;

  h3 {
    font-size: 3rem;
    line-height: 3.5rem;
    margin-bottom: 40px;
    transform: translate(-70px);
    width: 85%;
  }

  h4 {
    font-family: var(--font-primary);
  }

  .cols {
    display: grid;
    grid-column-gap: 20px;
    grid-template-columns: repeat(2, 1fr);
    grid-template-rows: 1fr;

    .col {
      &-left {
        grid-area: 1 / 1 / 2 / 2;
      }

      &-right {
        grid-area: 1 / 2 / 2 / 3;
      }
    }
  }
}
</style>
