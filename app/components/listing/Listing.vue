<template>
  <section class="listing">
    <div class="listing__container">
      <h2 class="listing__title section-title">Блог</h2>
      <div class="listing__article-list">
        <slot />
      </div>
      <NuxtLink to="#" class="listing__link link link--all">
        <span class="link__name">Смотреть все</span>
      </NuxtLink>
    </div>
  </section>
</template>

<style lang="less">
  .listing {
    padding-bottom: 100px;

    &__container {
      .container(); /* ✅ Вот он, миксин с отступами */
    }

    &__article-list {
      display: flex;
      flex-direction: column;
      margin-bottom: 60px;
    }

    &__link {
      margin-top: 40px;
      display: flex;
      justify-content: flex-end;
    }
  }
</style>
