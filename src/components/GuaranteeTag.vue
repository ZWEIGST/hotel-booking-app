<script></script>
<template>
  <div class="tag">
    <span class="tag__text">Гарантия лучшей цены!</span>
    <svg width="36" height="30" viewBox="0 0 36 30" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path
        fill-rule="evenodd"
        clip-rule="evenodd"
        d="M21.3018 0H0V30H21.3568C21.9628 30 22.5453 29.7604 22.9825 29.3313L35.2782 17.2634C36.214 16.3449 36.2438 14.8246 35.3447 13.8686L22.9939 0.736539C22.5513 0.26595 21.9403 0 21.3018 0ZM14.085 19.2C16.6779 19.2 18.7799 17.051 18.7799 14.4C18.7799 11.749 16.6779 9.6 14.085 9.6C11.492 9.6 9.38997 11.749 9.38997 14.4C9.38997 17.051 11.492 19.2 14.085 19.2Z"
        fill="#FF7647"
      />
    </svg>
  </div>
</template>
<style lang="scss" scoped>
@keyframes fadeInUp {
  0% {
    opacity: 0;
    transform: translateY(5px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}

.tag {
  display: flex;
  animation: 200ms fadeInUp;
  &__text {
    border-top-left-radius: 3px;
    border-bottom-left-radius: 3px;
    padding: 4px 4px 5px 16px;
    background-color: $colorAccent;
    font-size: 14px;
    line-height: 21px;
    font-weight: 700;
  }
}
</style>
