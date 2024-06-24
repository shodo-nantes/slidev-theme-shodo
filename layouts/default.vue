<!--
  Usage:
```md
---
```yaml
layout: default
```

<content>
-->

<template>
  <section class="slidev-layout default">
    <article>
      <slot />
    </article>
  </section>
  <slides-current-number />
</template>

<style>
.slidev-layout.default {
  padding: 7.5rem 8rem 6rem;

  h3 {
    font-size: 3rem;
    margin-bottom: 40px;
    transform: translate(-70px);
  }

  ul {
    margin: 30px 0;
  }
}
</style>
