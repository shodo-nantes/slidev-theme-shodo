<!--
  Usage:
```md
---
```yaml
layout: statement
(optional) slogan: <your slogan>
```

### <big concept>

<subtitle>
-->
<script setup lang="ts">
const props = defineProps({
  slogan: {
    type: String,
    default: "Crafting sustainable code we do"
  }
});
</script>

<template>
  <div class="slidev-layout statement">
    <div>
      <big-concept :slogan="slogan" />
      <slot />
    </div>
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.statement {
  padding: 1.5rem 5rem 6rem;
  text-align: center;

  h3 {
    font-size: 4.5rem;
    margin-bottom: 50px;
  }

  p {
    margin: auto;
    max-width: 80%;
  }
}
</style>
