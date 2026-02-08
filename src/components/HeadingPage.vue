<script setup></script>

<template>
  <div class="hotels-section">
    <h1 class="hotels-section__heading">Номера и цены</h1>
  </div>
</template>

<style lang="scss" scoped> 
@import '../assets/styles/variables.scss';
.hotels-section {
    display: flex;
    justify-content: center;
    &__heading {
        text-transform: uppercase;
        color: $colorTextHeading;
        font-family: "Roboto", sans-serif;
        font-size: $textSizeHeading1;
        font-weight: medium;
    }
}

</style>
