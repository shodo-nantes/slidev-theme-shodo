<!--
  Usage:
```md
---
```yaml
layout: screenshot
(optional) layoutClass: "laptop" or "mobile"
screenshot: <image local name> | <remote url>
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
    default: "laptop"
  },
  screenshot: {
    type: String,
    default: ""
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
        <div class="col-center-frame">
          <img :src="screenshot" alt="screenshot" />
        </div>
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
  align-items: center;
  display: flex;
  padding: 2rem;

  h4 {
    font-family: var(--font-primary);
  }

  .cols {
    display: grid;
    grid-column-gap: 40px;
    grid-template-columns: 1fr 2fr 1fr;
    grid-template-rows: 1fr;

    .col {

      &-left,
      &-center,
      &-right {
        align-items: center;
        display: flex;
        justify-content: center;
      }

      &-left {
        grid-area: 1 / 1 / 2 / 2;
        padding-left: 40px;
      }

      &-center {
        grid-area: 1 / 2 / 2 / 3;
        padding: 0 20px;
        position: relative;
      }

      &-right {
        grid-area: 1 / 3 / 2 / 4;
        padding-right: 40px;
      }
    }
  }

  &.laptop .col-center-frame {
    >img {
      object-fit: cover;
      max-width: 400px;
    }

    &::after {
      background-image: url("/macbook-air-frame.png");
      background-size: 100%;
      background-repeat: no-repeat;
      content: "";
      height: calc(100% * 2.3);
      left: -40px;
      position: absolute;
      top: -20px;
      width: calc(100% * 1.2);
    }
  }

  &.mobile .col-center-frame {
    >img {
      border-radius: 37px;
      max-height: 475px;
      object-fit: cover;
    }

    &::after {
      background-image: url("/iphone-15-pro-max-frame.png");
      background-size: 56%;
      background-repeat: no-repeat;
      content: "";
      height: calc(100% * 1.1);
      left: 93px;
      position: absolute;
      top: -5px;
      width: 100%;
    }
  }


}
</style>
