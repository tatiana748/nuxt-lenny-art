<template>
  <header class="main-header">
    <h1 class="main-header__title">Арт - пространство</h1>
    <picture class="main-header__picture">
   <img src="/images/LENNI.svg" class="main-header__img" alt="иконка LENNI" />
    </picture>
    <p class="main-header__text">
      для людей, горящих сердцем и делом место для настоящего
    </p>
  </header>
</template>

<style lang="less">
  .main-header {
    padding: 100px 0;
    @media @bw1340 { padding: 80px 0; }
    @media @bw768 { padding: 38px 0; }

    &__title,
    &__text {
      padding-left: 40px;
      padding-right: 40px;
      text-align: center;
      text-transform: uppercase;
      font-family: @font2;
      font-weight: 400;
      font-size: 45px;
      line-height: normal;
      color: @black;

      @media @bw1340 { font-size: 30px; }
      @media @bw768 { font-size: 13px; }
    }

    &__title {
      margin: 0 0 70px;
      @media @bw1340 { margin: 0 0 57px; }
      @media @bw768 { margin: 0 0 30px; }
    }

    &__text {
      margin: 0 auto;
      max-width: 1000px;
      width: 100%;
      padding-top: 70px;
      @media @bw1340 { padding-top: 49px; }
      @media @bw768 { padding-top: 28px; line-height: 16.64px; }
    }

    &__picture {
      display: block;
      margin-bottom: 70px;
      position: relative;
      width: 100%;
      @media @bw768 { margin-bottom: 30px; }

      &::before {
       content: "";
       display: block;
       width: 100%;
        padding-top: 16.927%;
     }
    }
    

    &__img {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: contain;
      
    }
  }
</style>