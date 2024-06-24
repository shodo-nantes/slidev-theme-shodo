<!--
  Usage:
```md
---
```yaml
layout: image-left
image: <img-path>
(optional) backgroundSize: default "cover"
```
<content>
-->

<script setup lang="ts">
import { computed } from "vue";
import { handleBackground } from "../node_modules/@slidev/client/layoutHelper";

const props = defineProps({
  image: {
    type: String,
  },
  class: {
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
  <div class="grid grid-cols-2 w-full h-full auto-rows-fr">
    <div class="w-full h-full" :style="style" />
    <div class="slidev-layout default" :class="props.class">
      <slot />
    </div>
    <slides-current-number />
  </div>
</template>
