<script setup></script>

<template>
  <div class="heading-container">
    <h1 class="heading-container__heading">Номера и цены</h1>
  </div>
</template>

<style lang="scss" scoped>
.heading-container {
  display: flex;
  justify-content: center;

  &__heading {
    text-transform: uppercase;
    color: $colorTextHeading;
    font-family: 'Roboto', sans-serif;
    font-size: $textSizeHeading1;
    font-weight: 500;

    @include mq('mobile') {
      font-size: $textSizeHeading3;
      line-height: 32px;
    }
  }
}
</style>
