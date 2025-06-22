<script lang="ts" setup>
import { onMounted, onUnmounted } from 'vue'
import StyledButton from '../ui/StyledButton.vue'

let parallaxElement: HTMLElement | null = null

const handleScroll = () => {
  if (!parallaxElement) return
  
  const scrolled = window.pageYOffset
  const parallaxSpeed = 0.5
  
  parallaxElement.style.transform = `translateY(${scrolled * parallaxSpeed}px)`
}

onMounted(() => {
  parallaxElement = document.querySelector('.hero-section')
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <div class="hero-container">
    <div class="hero-section">
      <!-- Hero -->
      <StyledButton text="Apply Now" />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.hero-container {
  height: 100vh;
  overflow: hidden;
}

.hero-section {
  width: 100%;
  height: 100vh;
  background-image: url('@/assets/images/apartments.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 2rem;
  position: relative;

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.4);
    z-index: 1;
  }

  > * {
    position: relative;
    z-index: 2;
  }
}
</style>