<script lang="ts" setup>
import LoanTabs from './LoanTabs.vue';
</script>

<template>
  <section class="rental-loans">
    <div class="content-container">
      <div class="left-content">
        <div class="text-content">
          <h1 class="main-title">RENTAL LOANS</h1>
          <div class="breadcrumb">
            <span>Full Income</span>
            <span class="separator">/</span>
            <span>Bank Statements</span>
            <span class="separator">/</span>
            <span>DSCR</span>
          </div>
        </div>
      </div>
      
      <div class="spacer"></div>
      <div class="spacer"></div>
      
      <div class="right-content">
        <LoanTabs />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.rental-loans {
  position: relative;
  min-height: 100vh;
  display: flex;
  align-items: flex-start;
  padding-top: 120px;
  background-image: url('@/assets/images/townhomes.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.content-container {
  position: relative;
  z-index: 2;
  max-width: 1600px;
  width: 100%;
  margin: 0 auto;
  padding: 0 45px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  gap: 40px;
  height: calc(100vh - 120px);
  align-items: stretch;
}

.left-content {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;

  .text-content {
    .main-title {
      font-family: 'Montserrat', sans-serif;
      font-size: 200px;
      font-weight: 800;
      color: #FFFFFF;
      line-height: 0.75;
      text-transform: uppercase;
      letter-spacing: -4px;
    }

    .breadcrumb {
      font-family: 'Lato', sans-serif;
      font-size: 20px;
      color: #FFFFFF;
      font-weight: 600;

      .separator {
        margin: 0 16px;
        color: #FFFFFF;
      }
    }
  }
}

.right-content {
  display: flex;
}

@media (max-width: 1200px) {
  .content-container {
    padding: 60px 32px;
    gap: 60px;
  }
}

@media (max-width: 992px) {
  .content-container {
    grid-template-columns: 1fr;
    gap: 40px;
    text-align: center;
  }

  .left-content {
    order: 1;
  }

  .right-content {
    order: 2;
  }
}

@media (max-width: 768px) {
  .content-container {
    padding: 40px 24px;
  }

  .left-content {
    .text-content {
      .breadcrumb {
        font-size: 16px;
        
        .separator {
          margin: 0 8px;
        }
      }
    }
  }
}

@media (max-width: 480px) {
  .content-container {
    padding: 32px 16px;
  }

  .left-content {
    .text-content {
      .breadcrumb {
        font-size: 14px;
        
        .separator {
          margin: 0 6px;
        }
      }
    }
  }
}
</style>