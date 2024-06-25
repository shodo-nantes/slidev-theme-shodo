<!--
  Usage:
```md
---
```yaml
layout: image-right
image: /<img-path>
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
    <div class="slidev-layout image-right" :class="props.class">
      <slot />
    </div>
    <div class="image-right-image" :style="style" />
    <slides-current-number />
  </div>
</template>

<style>
.slidev-layout.image-right {
  padding: 5rem 4rem;

  h3 {
    font-size: 3rem;
    line-height: 3rem;
    margin-bottom: 40px;
  }
}

.image-right-image {
  height: 100%;
  width: 100%;
}
</style>
