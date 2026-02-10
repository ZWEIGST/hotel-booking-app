<script setup>
import Heading from './Heading.vue'
import RoomCard from './RoomCard.vue'

import hotelImage1 from '../assets/img/Pic1.png'
import hotelImage2 from '../assets/img/Pic2.png'
import hotelImage3 from '../assets/img/Pic3.png'

const rooms = [
  {
    id: 1,
    img: hotelImage1,
    name: 'Представительский люкс',
    description: 'Эксклюзивный номер с панорамным видом на центр города Москвы',
    price: '7 900',
  },
  {
    id: 2,
    img: hotelImage2,
    name: 'Дуплекс',
    description: 'Просторный двухкомнатный номер с шикарным видом на парк',
    price: '5 700',
    hasGuaranteeTag: true,
  },
  {
    id: 3,
    img: hotelImage3,
    name: 'Бизнес-люкс',
    description: 'Трёхкомнатный номер с панорамным видом на Москва-реку',
    price: '4 900',
  },
]
</script>

<template>
  <div class="hotel-page-container">
    <Heading />
    <div class="hotel-cards-container">
      <RoomCard
        v-for="room in rooms"
        :key="room.id"
        :price="room.price"
        :img="room.img"
        :room-name="room.name"
        :room-description="room.description"
        :has-guarantee-tag="room.hasGuaranteeTag"
      />
    </div>
  </div>
</template>

<style lang="scss">
.hotel-page-container {
  padding: 24px 50px;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  justify-content: center;

  @include mq('tablet') {
    padding: 27px 34px;
  }

  @include mq('mobile') {
    padding: 24px 16px;
  }
}
.hotel-cards-container {
  margin-top: 32px;
  display: flex;
  gap: 32px;
  flex-wrap: wrap;
  justify-content: center;

  @include mq('tablet') {
    gap: 28px;
    margin-top: 26px;
  }

  @include mq('mobile') {
    gap: 32px;
    margin-top: 24px;
  }
}
</style>
