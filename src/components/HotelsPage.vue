<script setup>
import HeadingPage from './HeadingPage.vue';
import HotelCard from './HotelCard.vue';
</script>

<template>
  <div class="hotel-page-container">
    <HeadingPage />
    <HotelCard 
    title="Представительский люкс"
    description="Эксклюзивный номер с панорамным видом на центр города Москвы"
    :price="7900"
    image=""
    />
  </div>
</template>

<style lang="scss">
    .hotel-page-container {
    background: linear-gradient(#4975A1, #4975A1);
    }
</style>
