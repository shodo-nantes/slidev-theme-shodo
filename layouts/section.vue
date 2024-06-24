<!--
  Usage:
```md
---
```yaml
layout: section
```

## Transition headline

<content>
-->
<script setup lang="ts">
const props = defineProps({
  index: {
    type: String,
    default: "1"
  }
});
</script>

<template>
  <section class="slidev-layout section">
    <title-number :index="index" />
    <slot />
  </section>
  <slides-current-number />
</template>

<style>
.slidev-layout.section {
  padding: 7.5rem 16rem 6rem;
  text-align: center;

  h2 {
    font-size: 3rem;
    line-height: 4rem;
    margin: 30px;
  }

  p {
    margin: 0.5rem;
  }
}
</style>
