<!--
  Usage:
```md
---
```yaml
layout: full
```

<content>
-->

<template>
  <div class="slidev-layout full">
    <slot />
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.full {
  height: 100%;
  width: 100;

  :slotted {
    height: 100%;
    width: 100;
  }
}
</style>
