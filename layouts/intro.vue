<!--
  Usage:
```md
---
```yaml
layout: intro
```

<content>
-->

<template>
  <section class="slidev-layout intro">
    <article>
      <header class="intro-header">
        <div class="arrow-circle-red" alt="arrow" />
        <h2>Hello!</h2>
      </header>
      <slot />
    </article>
  </section>
  <slides-current-number />
</template>

<style>
.slidev-layout.intro {
  padding: 1rem 19rem 6rem;

  .intro-header {
    align-items: center;
    display: flex;
    justify-content: flex-start;
    margin-bottom: 40px;
    transform: translate(-16%);
  }

  h2 {
    font-size: 7rem;
    margin: 30px;
  }

  p {
    margin: 0.5rem;
  }
}
</style>
