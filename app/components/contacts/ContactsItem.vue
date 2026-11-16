<template>
  <div class="contacts-item">
    <div class="contacts-item__img">
      <SvgIcon :name="icon" width="24" height="24" />
    </div>
    <div class="contacts-item__content">
      <h4 class="contacts-item__title">{{ title }}</h4>
      <slot />
    </div>
  </div>
</template>

<script setup>
  defineProps({
    icon: { type: String, required: true },
    title: { type: String, required: true }
  });
</script>

<style lang="less">
  .contacts-item {
    display: flex;
    align-items: center;
    gap: 54px;
    
    &__img {
      display: flex;
      justify-content: center;
      align-items: center;
      width: 110px;
      height: 110px;
      background-color: @black;
      color: @red;
    }
    
    &__title {
      margin: 0 0 10px;
      font-weight: 600;
      font-size: 20px;
      color: @black;
    }
    
    &__content {
      flex-grow: 1;
    }
  }
</style>