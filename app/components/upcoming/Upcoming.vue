<template>
  <section class="upcoming">
    <div class="upcoming__container">
      <h2 class="upcoming__title section-title">Мероприятия</h2>
      
      <div class="upcoming__swiper swiper swiper--3s js-swiper">
        <div class="swiper-wrapper">
          <div class="swiper-slide" v-for="event in events" :key="event.slug">
            <EventCard :data="event" />
          </div>
        </div>
        
        <footer class="swiper-footer">
          <button type="button" class="swiper-arrow-prev arrow arrow--left">
            <SvgIcon class="arrow__icon" name="arrow_down" width="92" height="62" />
          </button>
          <div class="swiper-pagination"></div>
          <button type="button" class="swiper-arrow-next arrow">
            <SvgIcon class="arrow__icon" name="arrow_down" width="92" height="62" />
          </button>
        </footer>
      </div>
      
      <div class="upcoming__look">
        <NuxtLink to="/events" class="upcoming__link link link--all">
          <span class="link__name">Смотреть все</span>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
  const events = ref([
    {
      slug: "nirvana",
      img: "/images/events/nirvana.jpg",
      img_webp: "/images/events/nirvana.webp",
      alt: "Nirvana",
      title: "Собираемся и слушаем альбом Nirvana",
      description: "Это третий альбом группы, выпущенный после смерти Курта Кобейна.",
      date: "2026-12-07T18:00:00.000+07:00",
    },
    {
      slug: "stuff",
      img: "/images/events/stuff.jpg",
      img_webp: "/images/events/stuff.webp",
      alt: "HowStuffWorks",
      title: "Есть тема, нужно обсудить с HowStuffWorks",
      description: "Один из самых популярных подкастов в мире.",
      date: "2026-12-14T18:30:00.000+07:00",
    },
    {
      slug: "sade",
      img: "/images/events/sade.jpg",
      img_webp: "/images/events/sade.webp",
      alt: "Sade",
      title: "Вечер | The Best of Sade",
      description: "Музыка группы имеет эклектичный характер.",
      date: "2026-12-16T20:00:00.000+07:00",
    },
    {
      slug: "malevich",
      img: "/images/events/malevich.jpg",
      img_webp: "/images/events/malevich.webp",
      alt: "Malevich",
      title: "Выставка Малевича в Томске",
      description: "Самая полная выставка с 1988 года.",
      date: "2026-12-23T20:00:00.000+07:00",
    },
  ]);
</script>

<style lang="less">
  .upcoming {
    position: relative;
    width: 100%;
    padding: 35px 0;
    overflow: hidden;
    
    &::before,
    &::after {
      content: "";
      display: block;
      position: absolute;
      top: 0;
      width: 0;
      height: 0;
      border-bottom: 35px solid fade(@white, 60%);
      z-index: 1;
    }

    &::before {
      left: 0;
      border-right: 34vw solid transparent;
    }

    &::after {
      right: 0;
      border-left: 66vw solid transparent;
    }

    &__container {
      .container();
      position: relative;
      display: flex;
      flex-wrap: nowrap;
      flex-direction: column;
      padding: 90px 0;
      background-color: fade(@white, 60%);
      z-index: 2;

      &::before,
      &::after {
        content: "";
        display: block;
        position: absolute;
        bottom: 0;
        width: 0;
        height: 0;
        border-top: 35px solid fade(@white, 60%);
        z-index: 1;
      }

      &::before {
        left: 0;
        border-right: 60vw solid transparent;
      }

      &::after {
        right: 0;
        border-left: 39vw solid transparent;
      }
    }

    &__title {
      margin-top: 80px;
    }

    &__look {
      display: flex;
      justify-content: flex-end;
      padding-top: 13px;
    }
  }

  .swiper-wrapper {
    display: flex;
    gap: 30px;
    overflow-x: auto;
  }

  .swiper-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 530px;
    max-width: 100%;
    margin: 70px auto 0;
  }

  .swiper-pagination-bullets.swiper-pagination-horizontal {
    position: relative;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    bottom: auto;
    left: auto;
    width: auto;
    margin: 0 auto;
    padding: 0 15px;
  }

  .swiper-pagination-bullet {
    width: 15px;
    height: 2px;
    border-top: 5px solid transparent;
    border-bottom: 5px solid transparent;
    border-radius: 2px;
    background-color: @gray_dark;
    background-clip: padding-box;
    opacity: 1;
  }

  .swiper-pagination-bullet.swiper-pagination-bullet-active {
    background-color: @black;
    background-clip: padding-box;
  }

  .swiper-pagination-horizontal.swiper-pagination-bullets .swiper-pagination-bullet {
    margin: 2px 3px;
  }

  .arrow {
    background-color: transparent;
    cursor: pointer;
    border: none;
    
    &--left {
      transform: rotate(180deg);
    }
  }
</style>