<!--
  Usage:
```md
---
```yaml
layout: three-rows
```

::top::
<strong>Top</strong>

This shows on the top

::center::
<strong>Center</strong>

This shows on the center

::bottom::
<strong>Bottom</strong>

This shows on the bottom
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
  <section class="slidev-layout three-rows" :class="layoutClass">
    <div class="rows">
      <div class="row-top" :class="props.class">
        <div class="arrow-circle-red" alt="arrow" v-if="$slots.top" />
        <div>
          <slot name="top" />
        </div>
      </div>
      <div class="row-center" :class="props.class">
        <div class="arrow-circle-red" alt="arrow" v-if="$slots.center" />
        <div>
          <slot name="center" />
        </div>
      </div>
      <div class="row-bottom" :class="props.class">
        <div class="arrow-circle-red" alt="arrow" v-if="$slots.bottom" />
        <div>
          <slot name="bottom" />
        </div>
      </div>
    </div>
    <slides-current-number />
  </section>
</template>

<style>
.slidev-layout.three-rows {
  padding: 5rem 10rem;

  strong {
    font-family: var(--font-secondary);
    font-size: 4rem;
    line-height: 4rem;
  }

  p {
    font-size: 1.2rem;
    margin: 0;
  }

  .rows {
    display: grid;
    grid-row-gap: 40px;
    grid-template-rows: 3fr;

    .row {
      &-header {
        padding-bottom: 10px;
      }

      &-top,
      &-center,
      &-bottom {
        align-items: center;
        display: flex;
        justify-content: flex-start;

        .arrow-circle-red {
          margin-right: 50px;
        }
      }
    }
  }
}
</style>
