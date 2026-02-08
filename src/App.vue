<script setup>
import HotelsPage from './components/HotelsPage.vue'
</script>

<template>
  <header></header>

  <main>
    <HotelsPage />
  </main>
</template>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background: linear-gradient(180deg, rgba(222, 237, 255, 0.6) 0%, rgba(166, 204, 250, 0.5) 100%);
}
a {
  text-decoration: none;
  color:$colorTextLink;
  &:hover {
    text-decoration: underline;
  }
  &:active {
    color: $colorTextLinkActive;
  }
}
</style>
