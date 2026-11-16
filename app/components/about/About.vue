<template>
  <section class="about">
    <div class="about__container">
      <h2 class="about__section-title section-title">О нас</h2>
      <div class="about__block">
        <h3 class="about__title">Проект «Millennials»</h3>
        <p class="about__text">
          Вдохновлен молодыми идейными людьми, увлеченными творчеством, эмоциями и
          желанием сделать мир лучше, проявить себя. У них есть талант и
          стремление, у нас возможность помочь им воплотить их мечту в реальность.
        </p>
      </div>
      <div class="about__block2">
        <picture class="about__picture">
          <img src="/images/p1.jpg" class="about__img" alt="p1" />
        </picture>
        <picture class="about__picture2">
          <img src="/images/p3.jpg" class="about__img" alt="p3" />
        </picture>
        <h3 class="about__title about__title--w868 about__title--2">
          Мы предоставляем площади для вашего мероприятия
        </h3>
        <p class="about__text about__text--2">
          И оказываем помощь с организацией, если вам это нужно.
          <br />
          Наша цель: вовлечь в культурную жизнь города как можно больше людей,
          помочь молодым ребятам сделать первые шаги к своей мечте и рассказать
          всем о том, что их волнует.
        </p>
      </div>
      <div class="about__block3">
        <picture class="about__picture3">
          <img src="/images/p2.jpg" class="about__img2" alt="p2" />
        </picture>
        <div class="about__block3--wrapper">
          <p class="about__text about__text--mb90">
            Мы уже успешно организовали и провели более 100 проектов. Посмотрите,
            как это было классно.
          </p>
          <a href="#" class="about__link link">
            <span class="link__name">Смотреть</span>
            <SvgIcon class="link__icon link__icon--about" name="arrow_down" width="91" height="60" />
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="less">
  .about {
    padding-bottom: 130px;
    &__container { .container(); }
    
    &__title {
      margin: 0 0 50px; color: @black; font-size: 44px; font-weight: 700;
      @media @bw1340 { font-size: 26px; margin: 0 0 48px; }
      @media @bw768 { font-size: 18px; margin: 0 0 27px; }
    }
    
    &__title--w868 {
      margin-bottom: 0; max-width: 868px; width: 100%;
      @media @bw1340 { padding: 40px 0 0; margin: 0; }
      @media @bw768 { max-width: 420px; padding-top: 30px; }
    }
    
    &__text {
      align-self: flex-end; margin: 0 0 100px; max-width: 870px; width: 100%;
      color: @black; font-size: 18px; font-weight: 400;
      @media @bw1340 { font-size: 16px; max-width: 637px; margin: 0 0 80px; }
      @media @bw768 { margin: 0 0 60px; }
    }
    
    &__text--2 {
      grid-area: text; margin-left: auto;
      @media @bw1340 { max-width: 350px; padding-left: 71px; }
      @media @bw768 { padding-left: 0; margin: 0; }
    }
    
    &__text--mb90 {
      margin-bottom: 150px;
      @media @bw1340 { margin-bottom: 0; max-width: 280px; }
      @media @bw768 { margin-bottom: 0; max-width: 900px; }
    }
    
    &__block2 {
      display: grid;
      grid-template-areas: "pic1 pic1 pic2" "title title pic2" "text text text";
      grid-template-columns: 1fr 1fr 404px;
      gap: 60px;
      @media @bw1340 { grid-template-areas: "pic1 pic1 pic1" "title title pic2" "text text pic2"; grid-template-columns: 1fr 1fr 262px; gap: 40px; }
      @media @bw768 { grid-template-areas: "pic1 pic1" "title title" "text text" "pic2 pic2"; grid-template-columns: 1fr 193px; gap: 30px; }
    }
    
    &__picture {
      grid-area: pic1; position: relative; display: block;
      &::before { content: ""; display: block; padding-top: 66.322%; }
    }
    
    &__picture2 {
      grid-area: pic2; align-self: flex-end; position: relative; display: block;
      &::before { content: ""; display: block; padding-top: 122.029%; }
      @media @bw1340 { align-self: flex-start; }
    }
    
    &__img { position: absolute; top: 0; left: 0; width: 100%; height: 100%; object-fit: contain; }
    
    &__block3 {
      display: flex; justify-content: space-between; align-items: flex-end; gap: 60px;
      @media @bw1340 { flex-direction: column; align-items: center; gap: 85px; }
      @media @bw768 { align-items: flex-start; gap: 50px; }
    }
    
    
    &__picture3 {
      position: relative; 
      box-sizing: border-box; 
      display: block; 
      max-width: 930px; 
      width: 100%; 
      padding: 18px 9px 0 49px;
      
      &::before { 
        content: ""; 
        position: absolute; 
        top: 0; 
        left: 0; 
        right: 0; 
        height: 65%; 
        background-color: @red; 
        z-index: 0; 
      }
      
      &::after { 
        content: ""; 
        display: block; 
        width: 100%; 
        padding-top: 40.86%; 
      }
    }
    
    &__img2 { 
      position: absolute; 
      top: 18px; 
      left: 49px; 
      right: 9px; 
      bottom: 0; 
      width: calc(100% - 58px); 
      object-fit: contain; 
      z-index: 1; 
    }
    
    &__block3--wrapper { max-width: 344px; width: 100%; }
  }
</style>