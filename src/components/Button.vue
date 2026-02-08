<script setup>
defineProps({
  buttonText: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <button class="button">
    {{ buttonText }}
  </button>
</template>

<style lang="scss" scoped>
@import '../assets/styles/variables.scss';
.button {
  border: none;
  background-color: $colorButtonPrimary;
  color: $colorTextPrimary;
  border-radius: 5px;
  padding: 12px 24px;
  font-size: $textSizeButton;
  font-weight: bold;
  &:hover {
    cursor: pointer;
    background-color: $colorButtonHover;
  }
  &:active {
    color: $colorButtonTextActive;
  }
}
</style>
