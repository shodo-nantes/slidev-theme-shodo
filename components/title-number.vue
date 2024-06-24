<script setup lang="ts">
defineProps({
  index: {
    type: String,
    default: "1",
  },
});
</script>

<template>
  <div class="circle-red">{{ index }}</div>
</template>

<style scoped>
.circle-red {
  background-color: var(--color-primary);
  border-radius: 1000px;
  box-sizing: border-box;
  color: #000;
  content: "";
  font-family: var(--font-secondary);
  font-size: 2.4rem;
  height: 60px;
  left: 25%;
  position: absolute;
  width: 60px;
  z-index: 0;
}
</style>
