<!--
  Usage:
```md
---
```yaml
layout: end
```

<content>
-->

<template>
  <section class="slidev-layout end">
    <article>
      <header class="end-header">
        <div class="arrow-circle-red" alt="arrow" />
        <h2>Thanks!</h2>
      </header>
      <div class="end-content">
        <div class="end-slot">
          <slot />
        </div>
        <watermark />
      </div>
    </article>
  </section>
  <slides-current-number />
</template>

<style>
.slidev-layout.end {
  padding: 1rem 19rem 6rem;

  .end-header {
    align-items: center;
    display: flex;
    justify-content: flex-start;
    margin-bottom: 40px;
    transform: translate(-16%);
  }

  h2 {
    font-size: 7rem;
    margin: 30px 30px 20px;
  }

  p {
    margin: 0.5rem;
  }

  .end-content {
    display: flex;

    .watermark {
      margin-left: 50px;
    }
  }
}
</style>
