<script setup>
defineProps({
  avatar: String,
  name: String,
  status: String,
  title: String,
  quote: String,
  theme: String,
});
</script>

<template>
  <article :class="['card', `card--${theme}`]">
    <header class="card__header">
      <img :src="`/images/${avatar}`" :alt="name" width="32" height="32" class="card__img" loading="eager">
      <div class="card__header-wrapper">
        <p class="card__name">{{ name }}</p>
        <small class="card__status">{{ status }}</small>
      </div>
    </header>
    <h2 class="card__title">{{ title }}</h2>
    <blockquote class="card__quote">
      <p class="card__text">{{ quote }}</p>
    </blockquote>
  </article>
</template>

<style lang="scss" scoped>
@use "../assets/styles/abstracts" as *;

.card {
  display: flex;
  flex-direction: column;
  padding: rem(32);
  height: 100%;
  border-radius: rem(8);

  &__header {
    display: flex;
    align-items: center;
    gap: rem(14);
    margin-bottom: rem(16);
  }

  &__img {
    width: rem(32);
    height: rem(32);
    object-fit: cover;
    border: 2px solid;
    border-color: transparent;
    border-radius: 50%;
  }

  &__name {
    margin: 0;
    font-size: rem(13);
    font-weight: 600;
    line-height: 1.4;
  }

  &__status {
    display: block;
    font-size: rem(11);
    opacity: .5;
  }

  &__title {
    z-index: 1;
    margin: 0 0 rem(16);
    font-size: rem(20);
    font-weight: 600;
    line-height: 1.2;
  }

  &__quote {
    margin: 0;
    padding: 0;
  }

  &__text {
    margin: 0;
    font-size: rem(13);
    line-height: 1.4;
    opacity: .7;

    &::before {
      content: "“ ";
    }

    &::after {
      content: " ”";
    }
  }

  &--daniel {
    color: $White;
    background: $Purple-500 ;
  }

  &--daniel &__img {
    border-color: $Purple-300;
  }


  &--jonathan {
    color: $White;
    background-color: $Grey-500;
  }

  &--jeanette {
    color: $Grey-400;
    background-color: $White;
  }

  &--patrick {
    color: $White;
    background-color: $Dark-blue;
  }

  &--patrick &__img {
    border-color: $Purple-500;
  }

  &--kira {
    color: $Grey-400;
    background-color: $White;
  }

  @media (width >=rem(1024)) {
    padding: rem(30);
    box-shadow: 40px 60px 50px -10px rgb(0, 0, 0, 10%);

    &--daniel {
      background: $Purple-500 url("/images/bg-pattern-quotation.svg") no-repeat top right rem(64);
    }
  }
}
</style>
