<script setup lang="ts">
defineProps({
  slogan: {
    type: String,
    default: "Crafting sustainable code we do",
  },
});
</script>

<template>
  <article class="big-concept">
    <div class="big-concept-slogan">{{ slogan }}</div>
  </article>
</template>

<style scoped>
.big-concept {
  align-items: center;
  background: url("/bg-home.svg") no-repeat center/contain;
  color: #fff;
  display: flex;
  height: 300px;
  justify-content: center;
  margin: 0 auto 50px;
  padding: 20px 50px;
  width: 350px;

  &-slogan {
    font-family: var(--font-secondary);
    font-size: 2rem;
    line-height: 2rem;
    margin: auto;
    max-width: 80%;
    text-align: left;
    text-transform: uppercase;
  }
}
</style>
