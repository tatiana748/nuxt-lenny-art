<template>
  <article class="event">
    <header class="event__header">
      <h1 class="event__title title">{{ data?.title }}</h1>

      <div class="event__about">
        <div class="event__info">
          <time v-if="datetime" :datetime="data.date" class="event__time">
            {{ datetime.date }}
          </time>
          <div class="event__info-text">{{ data?.location }}</div>
        </div>

        <picture class="event__picture">
          <source type="image/webp" :srcset="data?.img_webp" />
          <img :src="data?.img" :alt="data?.alt" class="event__image" />
        </picture>

        <div class="event__info">
          <span v-if="datetime" class="event__time" data-caption="начало">
            {{ datetime.time }}
          </span>
          <div class="event__info-text">{{ data?.address }}</div>
        </div>
      </div>
    </header>

    <div class="event__container">
      <div class="content event__content" v-html="data?.content"></div>
    </div>
  </article>
</template>

<script setup>
  const slug = computed(() => useRoute().params.event);
  const URL = computed(
    () => `${useRequestURL().origin}/json/events/${slug.value}.json`,
  );

  const { data } = await useFetch(URL);

  const datetime = computed(() => {
    try {
      const date = new Date(data.value.date);
      return {
        date: date.toLocaleDateString(),
        time: date.toLocaleTimeString("ru-RU", {
          hour: "2-digit",
          minute: "2-digit",
        }),
      };
    } catch {
      return null;
    }
  });
</script>

<style lang="less">
  .event {
    padding: 40px 0 150px;
  }

  .event__container {
    box-sizing: border-box;
    width: 100%;
    max-width: 1414px;
    margin-left: auto;
    margin-right: auto;
    padding-left: 40px;
    padding-right: 40px;
  }

  .event__header {
    box-sizing: border-box;
    width: 100%;
    max-width: 1414px;
    margin-left: auto;
    margin-right: auto;
    padding-left: 40px;
    padding-right: 40px;
    margin-bottom: 80px;
  }

  .event__title {
    margin: 0 0 80px;
    font-family: @font2;
    font-weight: 500;
    font-size: 70px;
    line-height: 90px;
    text-align: center;
  }

  .event__about {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-bottom: 80px;
  }

  .event__info {
    flex-shrink: 0;
    box-sizing: border-box;
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    padding: 13px 0;
    text-align: right;
    text-transform: uppercase;
    font-family: @font3;
    font-weight: 300;
  }

  .event__info::before,
  .event__info::after {
    content: "";
    position: absolute;
    right: 0;
    display: block;
    width: 140px;
    max-width: 100%;
    height: 1px;
    background-image: linear-gradient(270deg, #1c1b1b 0%, rgba(255, 255, 255, 0) 82.876%);
  }

  .event__info::before {
    top: 0;
  }

  .event__info::after {
    bottom: 0;
  }

  .event__info:last-child {
    align-items: flex-start;
    text-align: left;
  }

  .event__info:last-child::before,
  .event__info:last-child::after {
    background-image: linear-gradient(90deg, #1c1b1b 0%, rgba(255, 255, 255, 0) 82.876%);
    left: 0;
    right: auto;
  }

  .event__time {
    font-size: 30px;
    font-style: normal;
    line-height: 36px;
    font-weight: 300;
  }

  .event__time[datetime]::after {
    content: attr(data-caption);
    margin-left: 10px;
    font-weight: 700;
    font-size: 16px;
    line-height: 19px;
  }

  .event__info-text {
    font-size: 16px;
    line-height: 19px;
    font-weight: 700;
  }

  .event__picture {
    display: block;
    width: 497px;
    margin: 0 50px;
  }

  .event__image {
    display: block;
    width: 100%;
  }

  .event__content {
    max-width: 830px;
    margin-bottom: 80px;
  }
</style>