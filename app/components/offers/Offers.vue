<template>
  <section class="offers">
    <div class="offers__container">
      <h4 class="offers__title">я хочу:</h4>
      <div class="offers__wrapper">
        <button type="button" class="offers__btn btn btn--red">
          Провести мероприятие
        </button>
        <button type="button" class="offers__btn btn">Стать арендатором</button>
      </div>
    </div>
  </section>
</template>

<style lang="less">
  .offers {
    &__container {
      box-sizing: border-box;
      width: 100%;
      max-width: 1414px;
      margin-left: auto;
      margin-right: auto;
      padding: 0 40px 208px;

      @media @bw1340 { padding: 0 30px 97px; }
      @media @bw768 { padding: 0 20px 88px; }
      @media @bw650 { padding: 0 0 88px; }
    }

    &__title {
      margin: 0 0 46px;
      text-align: center;
      font-family: @font2;
      font-size: 22px;
      font-weight: 400;
      line-height: 30px;
      text-transform: uppercase;
      color: @black;

      @media @bw1340 { font-size: 20px; margin: 0 0 0px; }
      @media @bw768 { font-size: 18px; line-height: 24px; }
      @media @bw600 { font-size: 16px; line-height: 20px; }
    }

    &__wrapper {
      display: flex;
      flex-direction: row;
      justify-content: center;
      gap: 107px;

      @media @bw1020 { gap: 52px; }
      @media @bw650 { flex-direction: column-reverse; gap: 25px; }
    }
  }
</style>