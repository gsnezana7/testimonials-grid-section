<script setup>
defineProps({
  avatar: String,
  name: String,
  status: String,
  title: String,
  quote: String,
  backgroundColor: String,
});
</script>

<template>
  <article class="card" :style="{ backgroundColor: backgroundColor }">
    <header class="card__header">
      <img :src="`/images/${avatar}`" alt="" class="card__img">
      <div class="card__header-text">
        <h2 class="card__title">{{ name }}</h2>
        <small class="card__">
          {{ status }}
        </small>
      </div>
    </header>
    <h3 class="card__subtitle">{{ title }}</h3>
    <blockquote>
      <p class="card__text">{{ quote }}</p>
    </blockquote>
  </article>
</template>

<style lang="scss" scoped>
@use "../assets/styles/abstracts" as *;
</style>
