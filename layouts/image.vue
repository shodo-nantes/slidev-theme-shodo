<!--
  Usage:
```md
---
```yaml
layout: image
image: /<img-path>
(optional) backgroundSize: default "cover"
```
-->

<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "../node_modules/@slidev/client/layoutHelper";

const props = defineProps({
  image: {
    type: String,
  },
  backgroundSize: {
    type: String,
    default: "cover",
  },
});

const style = computed(() =>
  handleBackground(props.image, false, props.backgroundSize),
);
</script>

<template>
  <div class="slidev-layout image" :style="style">
    <slot />
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.image {
  height: 100%;
  text-align: center;
  width: 100%;

  p {
    color: #000;
  }
}
</style>
