<template>
  <div class="doit">
    <div class="doit__text1">
      <p class="doit__text">Просто делайте,</p>
      <p class="doit__text doit__text--r">что нравится,</p>
    </div>
    <p class="doit__text doit__text--mt20">а мы вам поможем</p>
  </div>
</template>

<style lang="less">
  .doit {
    display: flex;
    flex-direction: column;
    margin-top: 150px;
    width: 100%;
    min-width: 2100px;

    @media @bw1340 {
      margin-top: 105px;
      min-width: 1485px;
    }
    @media @bw1020 {
      min-width: 867px;
    }
    @media @bw600 {
      min-width: 428px;
    }

    &__text1 {
      display: flex;
      flex-direction: row;
      gap: 90px;
      @media @bw1020 {
        flex-direction: column;
        gap: 13px;
      }
    }

    &__text {
      margin: 0 0 0 -50px;
      color: @black;
      font-family: @font3;
      font-size: 128px;
      font-weight: 700;
      line-height: 120%;
      white-space: nowrap;

      @media @bw1340 { font-size: 90px; }
      @media @bw1020 { font-size: 80px; margin: 0 0 0 -30px; }
      @media @bw600 { font-size: 45px; margin-left: -7px; }
    }

    &__text--r { text-align: right; }
    &__text--mt20 { margin-top: 20px; margin-left: -3px; }
  }
</style>