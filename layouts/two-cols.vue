<!--
  Usage:
```md
---
```yaml
layout: two-cols
```

# Left
This shows on the left

::right::
# Right
This shows on the right
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
  <div class="slidev-layout two-columns" :class="props.layoutClass">
    <div class="cols">
      <div class="col-left" :class="props.class">
        <slot name="left" />
      </div>
      <div class="col-right" :class="props.class">
        <slot name="right" />
      </div>
    </div>
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.two-columns {
  .cols {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
