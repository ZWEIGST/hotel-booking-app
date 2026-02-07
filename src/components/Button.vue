<script setup>
defineProps({
    buttonText: {
        type: String,
        required: true,
    }
  })
</script>

<template>
  <button class="button">
    {{ buttonText }}
  </button>
</template>

<style lang="scss" scoped>
.button {
  border: none;
  background-color: $colorButtonPrimary;
  color: $colorTextPrimary;
  max-height: 48px;
  max-width: 180px;
  font-size: $textSizeButton;
}
</style>
