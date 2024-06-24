<!--
  Usage:
```md
---
```yaml
layout: three-cols
```

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
  <section class="slidev-layout three-cols" :class="layoutClass">
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
.slidev-layout.three-cols {
  padding: 2rem;

  &.centered {
    align-items: center;
    display: flex;

    .col-left,
    .col-center,
    .col-right {
      align-items: center;
      display: flex;
      justify-content: center;
    }
  }

  h4 {
    font-family: var(--font-primary);
  }

  .cols {
    display: grid;
    grid-column-gap: 20px;
    grid-template-columns: 1fr 2fr 1fr;
    grid-template-rows: 1fr;

    .col {
      &-left {
        grid-area: 1 / 1 / 2 / 2;
        ;
      }

      &-center {
        grid-area: 1 / 2 / 2 / 3;
        position: relative;
      }

      &-right {
        grid-area: 1 / 3 / 2 / 4;
      }
    }
  }
}
</style>
