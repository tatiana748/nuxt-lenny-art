<template>
  <section class="contacts">
    <div class="contacts__container">
      <h2 class="contacts__title section-title">контакты</h2>
      <div class="contacts__wrapper">
        <div class="contacts__items">
          <ContactsItem icon="location" title="Томск, Белая 8">
            <p class="contacts-item__info">2 этаж</p>
            <p class="contacts-item__info">оф. 207-208</p>
          </ContactsItem>
          <ContactsItem icon="star" title="Отдел аренды">
            <a href="#" class="contacts-item__info">+7 499 350 0730</a>
            <a href="#" class="contacts-item__info">hi@tagree.ru</a>
          </ContactsItem>
          <ContactsItem icon="home" title="Отдел мероприятий">
            <a href="#" class="contacts-item__info">+7 499 350 0730</a>
            <a href="#" class="contacts-item__info">hi@tagree.ru</a>
          </ContactsItem>
        </div>
        <div class="contacts__map" id="js-contactsMap"></div>
      </div>
    </div>
  </section>
</template>

<style lang="less">
  .contacts {
    &__container {
      .container();
    }
    
    &__title {
      margin-bottom: 160px;
    }
    
    &__wrapper {
      display: flex;
      justify-content: space-between;
    }
    
    &__items {
      display: flex;
      flex-direction: column;
      gap: 67px;
      margin-right: 30px;
    }
    
    &__map {
      width: calc(100% - 578px);
      min-height: 300px;
      background-color: #ccc; /* Заглушка вместо карты */
    }
  }
</style>