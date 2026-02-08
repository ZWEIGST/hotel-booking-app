<script setup>
import Button from './Button.vue'

import hotelImage1 from '../assets/img/Pic1.png'
import hotelImage2 from '../assets/img/Pic2.png'
import hotelImage3 from '../assets/img/Pic3.png'

const hotels = [
  {
    id: 1,
    img: hotelImage1,
    class: 'Представительский люкс',
    description: 'Эксклюзивный номер с панорамным видом на центр города Москвы',
    price: '7 900',
  },
  {
    id: 2,
    img: hotelImage2,
    class: 'Дуплекс',
    description: 'Просторный двухкомнатный номер с шикарным видом на парк',
    price: '5 700',
  },
  {
    id: 3,
    img: hotelImage3,
    class: 'Бизнес-люкс',
    description: 'Трёхкомнатный номер с панорамным видом на Москва-реку',
    price: '4 900',
  },
]
</script>

<template>
  <div class="card-container">
    <div v-for="hotel in hotels" :key="hotel.id" class="card-container__hotel">
      <img class="card__img" :src="hotel.img" alt="интерьер отеля" />
      <div class="card__img--gradient"></div>
      <div class="card-container__text-content">
        <h3 class="card__heading">
          {{ hotel.class }}
        </h3>
        <p class="card__decription">
          {{ hotel.description }}
        </p>
        <div class="card__book-container">
          <div class="card__price-container">
            <p class="card__rate">Цена за сутки</p>
            <div class="card__price-section">
              <h4 class="card__start-price">от</h4>
              <h3 class="card__price">
                {{ hotel.price.replace(' ', '&nbsp;') }}
              </h3>
              <p class="card__value-price">₽</p>
            </div>
          </div>
          <Button class="card__button" buttonText="Забронировать" />
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import '../assets/styles/variables.scss';
h3,
h4,
p {
  font-family: 'Open Sans', sans-serif;
}
.card {
  &-container {
    display: flex;
    gap: 32px;
    &__hotel {
      display: grid;
      grid-template-rows: repeat(2, 1fr);
      color: $colorTextPrimary;
      position: relative;
      width: 100%;
      max-height: 372px;
      aspect-ratio: 1 / 1;
    }
    &__text-content {
      padding: 24px;
      grid-row: 2;
    }
  }
  &__img {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: 1;
    &--gradient {
      position: absolute;
      background: linear-gradient(180deg, #0a2240 10%, #0a2240 100%);
      z-index: 2;
    }
  }
  &__heading {
    color: $colorTextPrimary;
    position: relative;
    font-weight: bold;
    z-index: 3;
  }
  &__decription {
    border-bottom: 1px solid $colorTextPrimary;
    padding-bottom: 20px;
    color: $colorTextPrimary;
    position: relative;
    z-index: 3;
  }
  &__book-container {
    display: flex;
    flex-direction: row;
    gap: 24px;
  }
  &__price-container {
    display: flex;
    flex-direction: column;
    gap: 6px;
  }
  &__rate {
    color: $colorTextPrimary;
    position: relative;
    font-weight: bold;
    flex-wrap: nowrap;
    z-index: 3;
  }
  &__price-section {
    display: flex;
    flex-direction: row;
    gap: 6px;
  }
  &__start-price {
    color: $colorTextPrimary;
    position: relative;
    font-weight: bold;
    z-index: 3;
  }
  &__price {
    color: $colorTextPrice;
    position: relative;
    font-weight: bold;
    z-index: 3;
  }
  &__value-price {
    color: $colorTextValuePrice;
    position: relative;
    font-weight: bold;
    z-index: 3;
  }
  &__button {
    position: relative;
    align-self: center;
    z-index: 3;
  }
}
</style>
