<script setup>
defineProps({
  buttonText: {
    type: String,
    required: true,
  },
  onClick: Function,
})
</script>

<template>
  <button class="button" @click.stop @click="onClick">
    {{ buttonText }}
  </button>
</template>

<style lang="scss" scoped>
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

  @include mq('mobile') {
    font-size: 14px;
  }
}
</style>
