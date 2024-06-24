<!--
  Usage:
```md
---
```yaml
layout: intro
```

<div class="subtitle">Shodo</div>

# This is your presentation title
-->

<template>
  <section class="slidev-layout cover">
    <article>
      <watermark />
      <slot />
    </article>
  </section>
</template>

<style>
.slidev-layout.cover {
  padding: 2.5rem 3.5rem 6rem;
  position: relative;
  width: 100%;

  .watermark {
    left: 15px;
    position: absolute;
    top: 15px;
  }
}
</style>
