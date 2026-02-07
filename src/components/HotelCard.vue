<script setup>
import Button from './Button.vue';

defineProps({
    hotelClass: {
        type: String,
        required: true,
    }
}
</script>

<template>
  <div class="card-container">
    <img src="" alt="интерьер отеля">
    <h3>
        {{ hotelClass }}
    </h3>
    <Button button-text="Забронировать"/>
  </div>
</template>

<style lang="scss"> </style>
