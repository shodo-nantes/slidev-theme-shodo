<!--
  Usage:
```md
---
```yaml
layout: intro
```

Quote text

Author name
-->

<template>
  <section class="slidev-layout quote">
    <slot />
  </section>
  <slides-current-number />
</template>

<style>
.slidev-layout.quote {
  padding: 7.5rem 16rem 6rem;
  text-align: center;

  p {
    font-family: var(--font-primary);
    font-size: 1.5rem;
    font-weight: 700;
    line-height: 2.5rem;
    margin: auto;
    position: relative;
    width: 70%;

    &:last-child {
      font-family: var(--font-secondary);
      font-size: 1.2rem;
      text-align: right;
    }

    &:first-child {
      font-style: italic;
      text-align: left;

      &::before {
        content: '"';
        font-family: var(--font-secondary);
        font-size: 6rem;
        font-style: normal;
        left: -50px;
        position: absolute;
        top: 30px;
      }
    }
  }
}
</style>
