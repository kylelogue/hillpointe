<script setup lang="ts">
import './assets/styles/base.scss';
import { RouterView } from 'vue-router'
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 0
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header>
    <div class="nav-container" :class="{ 'scrolled': isScrolled }">
      <div class="nav">
        <div class="logo" />
      </div>
    </div>
  </header>
  <RouterView />
</template>

<style lang="scss" scoped>
.nav-container {
  width: 100%;
  position: fixed;
  top: 0;
  padding: 15px;
  z-index: 1;
  transition: all 0.5s;

  &.scrolled {
    background-color: #555555;
  }
}
.nav {
  max-width: 1600px;
  margin: 0 auto;
  .logo {
    background: url('@/assets/images/hillpointe-white-branding.png');
    background-repeat: no-repeat;
    background-size: contain;
    height: 40px;
  }
}
</style>
