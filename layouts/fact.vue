<!--
  Usage:
```md
---
```yaml
layout: fact
```

<content>
-->

<template>
  <div class="slidev-layout fact">
    <div>
      <slot />
    </div>
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.fact {
  >div {
    margin-top: auto;
    margin-bottom: auto;
  }
}
</style>
