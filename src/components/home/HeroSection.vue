<script lang="ts" setup>
import { onMounted, onUnmounted } from 'vue';
import StyledButton from '../ui/StyledButton.vue';

let heroSection: HTMLElement | null = null;

const handleScroll = () => {
  if (!heroSection) return;
  
  const scrolled = window.pageYOffset;
  const parallaxSpeed = 0.5;
  
  heroSection.style.setProperty('--parallax-offset', `${scrolled * parallaxSpeed}px`);
};

onMounted(() => {
  heroSection = document.querySelector('.hero-content');
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<template>
  <section class="hero-container">
    <div class="hero-content">
      <div class="content-wrapper">
        <div class="heading-container">
          <p class="heading">Building <span class="accent">More</span> Communities</p>
          <p class="subheading">Integrated Development For <span class="accent">Smart Investment</span></p>
        </div>
        <StyledButton
          class="cta"
          text="Get Started"
          size="large"
          color="blue"
        />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hero-container {
  height: 100vh;
  min-height: 600px;
  overflow: hidden;
}

.hero-content {
  position: relative;
  width: 100%;
  height: 100vh;
  min-height: 600px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  color: white;
  --parallax-offset: 0px;

  .content-wrapper {
    max-width: 1600px;
    width: 100%;
    margin: 0 auto;
    padding: 0 45px;
    position: relative;
    z-index: 3;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
  }

  .heading-container {
    width: 100%;
    
    .heading {
      font-size: clamp(60px, 12vw, 250px);
      font-weight: 600;
      line-height: 0.8;
      text-transform: uppercase;
      margin: 0 0 20px 0;
      max-width: 900px; // Fixed max-width instead of percentage
    }
    
    .subheading {
      font-size: clamp(18px, 3vw, 28px);
      font-weight: 400;
      margin: 0 0 40px 0;
      line-height: 1.2;
      max-width: 600px; // Fixed max-width for subheading too
    }
    
    .accent {
      color: #5CA4E9;
      font-weight: 700;
    }
  }

  .cta {
    margin-top: 20px;
  }

  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    height: 120vh;
    background-image: url('@/assets/images/apartments.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    transform: scaleX(-1) translateY(var(--parallax-offset));
    z-index: 1;
  }

  &::after {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.4);
    z-index: 2;
  }
}

// Responsive breakpoints
@media (max-width: 1200px) {
  .hero-content {
    .heading-container {
      .heading {
        max-width: 800px;
      }
      .subheading {
        max-width: 500px;
      }
    }
  }
}

@media (max-width: 992px) {
  .hero-content {
    .content-wrapper {
      padding: 0 32px;
    }
    
    .heading-container {
      .heading {
        line-height: 0.9;
        max-width: 700px;
      }
      .subheading {
        max-width: 450px;
      }
    }
  }
}

@media (max-width: 768px) {
  .hero-container {
    min-height: 500px;
  }
  
  .hero-content {
    min-height: 500px;
    justify-content: center;
    
    .content-wrapper {
      padding: 0 24px;
      align-items: center;
      text-align: center;
    }
    
    .heading-container {
      .heading {
        line-height: 1;
        margin-bottom: 16px;
        max-width: none; // Remove max-width on mobile
      }
      
      .subheading {
        margin-bottom: 32px;
        line-height: 1.3;
        max-width: none; // Remove max-width on mobile
      }
    }
  }
}

@media (max-width: 480px) {
  .hero-container {
    min-height: 450px;
  }
  
  .hero-content {
    min-height: 450px;
    
    .content-wrapper {
      padding: 0 16px;
    }
    
    .heading-container {
      .heading {
        margin-bottom: 12px;
      }
      
      .subheading {
        margin-bottom: 24px;
      }
    }
  }
}

// Landscape orientation on mobile
@media (max-height: 500px) and (orientation: landscape) {
  .hero-container {
    min-height: 400px;
  }
  
  .hero-content {
    min-height: 400px;
    
    .heading-container {
      .heading {
        font-size: clamp(40px, 8vw, 120px);
      }
      
      .subheading {
        font-size: clamp(14px, 2.5vw, 20px);
        margin-bottom: 20px;
      }
    }
  }
}
</style>