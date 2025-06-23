<script setup lang="ts">
import './assets/styles/base.scss';
import { RouterView } from 'vue-router';
import { ref, onMounted, onUnmounted } from 'vue';
import StyledButton from './components/ui/StyledButton.vue';
import SidebarMenu from './components/ui/SidebarMenu.vue';
import logoImage from '@/assets/images/hillpointe-white-branding.png';

const isScrolled = ref(false);

const handleScroll = () => {
  isScrolled.value = window.scrollY > 0;
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <header>
    <div
      class="nav-container"
      :class="{ 'scrolled': isScrolled }"
    >
      <div class="nav">
        <div class="logo">
          <img 
            :src="logoImage" 
            alt="Hillpointe Logo" 
            class="logo-image"
          />
        </div>
        <div class="buttons">
          <div class="desktop-buttons">
            <StyledButton
              text="Contact Us"
              color="dark"
              rounded
            />
            <StyledButton
              text="Apply Now"
              color="light"
              rounded
            />
          </div>
          <SidebarMenu />
        </div>
      </div>
    </div>
  </header>
  <RouterView />
</template>

<style>
.no-scroll {
  overflow: hidden;
  height: 100vh;
}
</style>

<style lang="scss" scoped>
.nav-container {
  width: 100%;
  position: fixed;
  top: 0;
  padding: 15px 0;
  z-index: 1000;
  transition: background 0.5s ease;

  &.scrolled {
    background: #357ABD;
  }
}

.nav {
  max-width: 1600px;
  margin: 0 auto;
  padding: 0 45px;
  display: flex;
  justify-content: space-between;
  align-items: center;

  .logo {
    flex-shrink: 0;

    .logo-image {
      height: 40px;
      width: auto;
      max-width: 350px;
    }
  }

  .buttons {
    display: flex;
    align-items: center;
    gap: 16px;

    .desktop-buttons {
      display: flex;
      gap: 16px;
    }
  }
}

@media (max-width: 1200px) {
  .nav {
    padding: 0 32px;

    .logo {
      .logo-image {
        max-width: 300px;
        height: 36px;
      }
    }
  }
}

@media (max-width: 992px) {
  .nav {
    padding: 0 24px;

    .logo {
      .logo-image {
        max-width: 250px;
        height: 32px;
      }
    }

    .buttons {
      .desktop-buttons {
        gap: 12px;
      }
    }
  }
}

@media (max-width: 768px) {
  .nav-container {
    padding: 12px 0;
  }

  .nav {
    padding: 0 20px;

    .logo {
      .logo-image {
        max-width: 200px;
        height: 28px;
      }
    }

    .buttons {
      .desktop-buttons {
        display: none;
      }
    }
  }
}

@media (max-width: 480px) {
  .nav {
    padding: 0 16px;

    .logo {
      .logo-image {
        max-width: 180px;
        height: 24px;
      }
    }
  }
}
</style>