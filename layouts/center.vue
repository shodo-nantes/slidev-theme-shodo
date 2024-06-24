<!--
  Usage:
```md
---
```yaml
layout: center
```

<content>
-->

<template>
  <div class="slidev-layout center">
    <div>
      <slot />
    </div>
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.center {
  display: grid;
  height: 100%;
  place-content: center;
  text-align: center;

  >div {
    margin-bottom: auto;
    margin-top: auto;
  }

  strong {
    font-family: var(--font-secondary);
    font-size: 7rem;
  }
}
</style>
