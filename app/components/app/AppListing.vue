<template>
  <section class="app-listing">
    <h1 class="app-listing__title section-title">{{ title }}</h1>
    <div class="app-listing__list">
      <slot />
    </div>
    <button type="button" class="more-btn app-listing__more-btn">
      Показать всё
      <SvgIcon class="more-btn__arrow" name="arrow_down" width="62" height="92" />
    </button>
  </section>
</template>

<script setup>
  const props = defineProps({
    title: { type: String, default: "" },
  });
</script>

<style lang="less">
   .app-listing {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;

    &__title {
      margin-top: 40px;
      margin-bottom: 40px;
    }

    &__list {
      display: flex;
      flex-wrap: wrap;
      justify-content: flex-start;
      width: 100%;
      margin-bottom: 60px;
      gap: 30px;
    }

    &__more-btn {
      margin-top: 20px;
    }
  }
</style>
