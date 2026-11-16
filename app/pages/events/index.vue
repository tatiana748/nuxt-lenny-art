<template>
  <div class="home">
    <MainHeader class="home__main-header" />
    <Offers class="home__offers" />
    <About class="home__about" />
    <Upcoming class="home__upcoming" />
    <Listing class="home__listing">
      <ArticleCard 
        v-for="(post, index) in posts" 
        :key="index" 
        :data="post" 
        class="listing__article-card"
      />
    </Listing>
    <Contacts class="home__contacts" />
    <Doit class="home__doit" />
  </div>
</template>

<script setup>
  const posts = ref([
    {
      img: "/images/Theatre.jpg",
      alt: "театр",
      datetime: "2022-11-26T00:00",
      time: "26.11.2022",
      title: "Фотосессия в стенах Театра драмы",
      description: "Организовывая фотосессию для локального бренда одежды мы смогли воплотить все пожелания заказчика."
    },
    {
      img: "/images/VR.jpg",
      alt: "vr",
      datetime: "2022-11-05T00:00",
      time: "05.11.2022",
      title: "Выставка VR в Томске",
      description: "Клуб виртуальной реальности - это другие миры, яркие эмоции, новый опыт."
    },
    {
      img: "/images/rockingRadio.jpg",
      alt: "rocking radio",
      datetime: "2022-11-01T00:00",
      time: "01.11.2022",
      title: "Rocking radio в заброшенном ангаре",
      description: "15 электрогенераторов, километры проводов и пару тонн света."
    }
  ]);
</script>

<style lang="less">
   .home {
    display: flex;
    flex-direction: column;
    width: 100%;
    overflow-x: hidden;
  }
</style>