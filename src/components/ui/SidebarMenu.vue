<script lang="ts" setup>
import { ref, watch } from 'vue';

const sidebarMenuOpen = ref(false);

const openSidebarMenu = () => {
  sidebarMenuOpen.value = true;
};
const closeSidebarMenu = () => {
  sidebarMenuOpen.value = false;
};

watch(sidebarMenuOpen, (isOpen) => {
  if (isOpen) {
    document.body.classList.add('no-scroll');
  } else {
    document.body.classList.remove('no-scroll');
  }
});
</script>

<template>
  <div class="sidebar-menu">
    <button
      class="toggle open"
      @click="openSidebarMenu"
    >&#9776;</button>
    
    <Transition name="slide">
      <div
        v-if="sidebarMenuOpen"
        class="menu"
      >
        <button
          class="toggle close"
          @click="closeSidebarMenu"
        >&times;</button>
        
        <nav class="menu-nav">
          <a
            href="#"
            class="nav-link"
            @click="closeSidebarMenu"
          >Investor Login</a>
          <a
            href="#"
            class="nav-link"
            @click="closeSidebarMenu"
          >Tenant Login</a>
          <a
            href="#"
            class="nav-link"
            @click="closeSidebarMenu"
          >The Team</a>
          <a
            href="#"
            class="nav-link"
            @click="closeSidebarMenu"
          >The Hillpointe Difference</a>
          <a
            href="#"
            class="nav-link"
            @click="closeSidebarMenu"
          >Project Portfolio</a>
          <a
            href="#"
            class="nav-link"
            @click="closeSidebarMenu"
          >Careers</a>
          <a
            href="#"
            class="nav-link"
            @click="closeSidebarMenu"
          >Media</a>
        </nav>
      </div>
    </Transition>
    
    <!-- Backdrop overlay -->
    <Transition name="fade">
      <div
        v-if="sidebarMenuOpen"
        class="backdrop"
        @click="closeSidebarMenu"
      ></div>
    </Transition>
  </div>
</template>

<style lang="scss" scoped>
.toggle {
  border: none;
  background: transparent;
  transition: all 0.2s ease;
  cursor: pointer;
  
  &.open {
    color: #FFFFFF;
    font-size: 32px;
  }

  &.close {
    position: absolute;
    font-size: 24px;
    top: 15px;
    right: 15px;
    color: #333333;
    
    &:hover {
      color: #000000;
    }
  }
}

.menu {
  position: fixed;
  right: 0;
  top: 0;
  width: 360px;
  height: 100vh;
  background: #FFFFFF;
  box-shadow: -2px 0 10px rgba(0, 0, 0, 0.1);
  z-index: 1001;
  padding: 60px 30px 30px 30px;
}

.menu-nav {
  display: flex;
  flex-direction: column;
  gap: 24px;
  margin-top: 20px;
}

.nav-link {
  text-decoration: none;
  color: #777777;
  font-size: 16px;
  font-weight: 500;
  padding: 12px 0;
  transition: all 0.2s ease;
  text-transform: uppercase;
  
  &:hover {
    color: #5CA4E9;
  }
  
  &:last-child {
    border-bottom: none;
  }
}

.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.5);
  z-index: 1000;
}

// Slide animation for menu
.slide-enter-active,
.slide-leave-active {
  transition: transform 0.3s ease;
}

.slide-enter-from {
  transform: translateX(100%);
}

.slide-leave-to {
  transform: translateX(100%);
}

// Fade animation for backdrop
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>