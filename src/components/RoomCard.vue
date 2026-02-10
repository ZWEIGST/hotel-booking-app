<script setup>
import { computed, ref } from 'vue'
import Button from './Button.vue'
import GuaranteeTag from './GuaranteeTag.vue'

const props = defineProps({
  img: {
    type: String,
    required: true,
  },
  roomName: {
    type: String,
    required: true,
  },
  roomDescription: {
    type: String,
    required: true,
  },
  price: {
    type: String,
    required: true,
  },
  hasGuaranteeTag: Boolean,
})

const isReserved = ref(false)
const hasMouseLeftAfterReservation = ref(false)
const isMouseOver = ref(false)

const toggleIsReserved = () => {
  isReserved.value = !isReserved.value
}
const onCardClick = () => {
  if (isReserved.value) {
    isReserved.value = false
    hasMouseLeftAfterReservation.value = false
  }
}
const onMouseLeave = () => {
  if (isReserved.value) {
    hasMouseLeftAfterReservation.value = true
  }
  isMouseOver.value = false
}
const onMouseOver = () => {
  isMouseOver.value = true
}

const isReservedLayoutVisible = computed(() => {
  return isReserved.value && hasMouseLeftAfterReservation.value
})
const isGuaranteeTagVisible = computed(() => {
  return props.hasGuaranteeTag && isMouseOver.value && !isReservedLayoutVisible.value
})
</script>

<template>
  <div class="card" @click="onCardClick" @mouseleave="onMouseLeave" @mouseover="onMouseOver">
    <img class="card__img" :src="img" alt="интерьер номера" />
    <div class="card__content-overlay"></div>
    <div v-if="isReservedLayoutVisible" class="card__reserved-overlay">
      <div class="card__reserved-text">
        <p>Номер зарезервирован</p>
        <p>Перейти к <a>оплате</a></p>
      </div>
    </div>
    <div v-if="isGuaranteeTagVisible" class="card__guarantee-tag"><GuaranteeTag /></div>
    <div class="card__text-content">
      <a href="/" class="card__title-link">
        <h3 class="card__title">
        {{ roomName }}
      </h3>
      </a>
      <p class="card__decription">
        {{ roomDescription }}
      </p>
      <div class="card__book-container">
        <div class="card__price-container">
          <p>Цена за сутки</p>
          <p class="card__price-line">
            от
            <span>
              <span class="card__price">
                {{ price.replace(' ', '&nbsp;') }}
              </span>
              <span class="card__currency">₽</span>
            </span>
          </p>
        </div>
        <Button class="card__button" buttonText="Забронировать" :on-click="toggleIsReserved" />
      </div>
    </div>
  </div>
</template>

<style lang="scss">
p {
  font-family: 'Open Sans', sans-serif;
}
.card {
  display: flex;
  align-items: flex-end;
  color: $colorTextPrimary;
  position: relative;
  width: 100%;
  max-width: 372px;
  height: 372px;
  border-radius: 10px;
  overflow: hidden;
  font-family: 'Roboto', sans-serif;

  @include mq('tablet') {
    height: 420px;
    max-width: 336px;
  }

  @include mq('mobile') {
    height: 347px;
    max-width: 100%;
  }

  &__guarantee-tag {
    position: absolute;
    top: 24px;
    left: 24px;
    z-index: 3;
  }
  &__text-content {
    padding: 24px;
    position: relative;
    z-index: 3;
  }
  &__img {
    position: absolute;
    width: 100%;
    height: 100%;
    object-fit: cover;
    z-index: 1;
  }
  &__content-overlay {
    position: absolute;
    width: 100%;
    height: 100%;
    z-index: 2;
    background: linear-gradient(180deg, rgba(10, 34, 64, 0.1) 0%, #0a2240 100%);
  }
  &__reserved-overlay {
    position: absolute;
    width: 100%;
    height: 100%;
    z-index: 4;
    background: #ffffff66;
    display: flex;
    align-items: flex-end;
  }
  &__reserved-text {
    width: 100%;
    padding: 26px 25px 32px;
    background-color: $colorSecondary;
    font-size: 14px;
    line-height: 21px;
    text-align: center;
  }
  &__title {
    font-weight: 700;
    font-size: 24px;
    line-height: 32px;
    &-link {
      color: $colorTextPrimary;
      &:hover {
        text-decoration: underline;
      }
      &:active {
        color: rgba(255, 255, 255, 0.5);
      }
    }

    @include mq('mobile') {
      font-size: 20px;
      line-height: 26px;
    }
  }
  &__decription {
    font-size: 16px;
    line-height: 24px;
    border-bottom: 1px solid #ffffff33;
    padding-bottom: 20px;
    margin-top: 9px;
    margin-bottom: 18px;
    font-family: 'Open Sans';

    @include mq('mobile') {
      font-size: 14px;
      line-height: 21px;
      margin-top: 10px;
    }
  }
  &__book-container {
    display: grid;
    grid-template-columns: 1fr 180px;
    gap: 24px;

    @include mq('tablet') {
      grid-template-columns: 1fr;
      gap: 16px;
    }
  }
  &__price-container {
    font-weight: 700;
    font-size: 16px;
    line-height: 24px;

    @include mq('mobile') {
      font-size: 14px;
      line-height: 21px;
    }
  }
  &__price-line {
    font-size: 19px;

    @include mq('mobile') {
      font-size: 17px;
    }
  }
  &__price,
  &__currency {
    font-size: 24px;
    line-height: 32px;
    margin-left: 6px;

    @include mq('mobile') {
      font-size: 20px;
    }
  }
  &__price {
    color: $colorTextPrice;
    font-weight: 700;
  }
  &__currency {
    color: $colorTextValuePrice;
    font-weight: 400;
    font-family: 'Roboto';
  }
  &__button {
    align-self: center;
  }
}
</style>
