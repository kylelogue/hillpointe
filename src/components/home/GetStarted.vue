<script lang="ts" setup>
import StyledButton from '../ui/StyledButton.vue';

interface ProcessStep {
  number: string;
  title: string;
  description: string;
}

const processSteps: ProcessStep[] = [
  {
    number: '01',
    title: 'Initial Consultation',
    description: 'Discuss your investment goals and portfolio objectives with our experienced team to understand your unique requirements.',
  },
  {
    number: '02',
    title: 'Market Analysis',
    description: 'We identify optimal investment opportunities across key Sun Belt markets using our proprietary research and data-driven insights.',
  },
  {
    number: '03',
    title: 'Investment Strategy',
    description: 'Develop a tailored investment approach that aligns with your risk profile and maximizes risk-adjusted returns.',
  },
  {
    number: '04',
    title: 'Project Execution',
    description: 'Full development, construction, and asset management with our vertically integrated platform ensuring superior execution.',
  },
];
</script>

<template>
  <section class="get-started">
    <div class="container">
      <div class="content-grid">
        <div class="title-section">
          <h2 class="main-title">GET STARTED</h2>
          <div class="cta-section">
            <p class="cta-description">
              Ready to unlock superior risk-adjusted returns with Hillpointe's 
              integrated investment platform?
            </p>
            <StyledButton 
              text="Contact Us Today" 
              color="blue" 
              size="large" 
              class="cta-button"
            />
          </div>
        </div>
        
        <div class="process-section">
          <div 
            v-for="step in processSteps" 
            :key="step.number"
            class="process-step"
          >
            <div class="step-number">{{ step.number }}</div>
            <div class="step-content">
              <h3 class="step-title">{{ step.title }}</h3>
              <p class="step-description">{{ step.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.get-started {
  padding: 120px 0;
  background: #f1f1f1;
}

.container {
  max-width: 1600px;
  margin: 0 auto;
  padding: 0 45px;
}

.content-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 100px;
  align-items: flex-start;
}

.title-section {
  .main-title {
    font-family: 'Montserrat', sans-serif;
    font-size: clamp(80px, 12vw, 160px);
    font-weight: 900;
    color: #333;
    line-height: 0.8;
    margin: 0 0 60px 0;
    text-transform: uppercase;
    letter-spacing: -4px;
  }

  .cta-section {
    .cta-description {
      font-family: 'Lato', sans-serif;
      font-size: 20px;
      font-weight: 400;
      line-height: 1.5;
      color: #666;
      margin: 0 0 32px 0;
    }

    .cta-button {
      display: inline-block;
    }
  }
}

.process-section {
  display: flex;
  flex-direction: column;
  gap: 48px;

  .process-step {
    display: flex;
    gap: 24px;
    align-items: flex-start;

    .step-number {
      font-family: 'Montserrat', sans-serif;
      font-size: 18px;
      font-weight: 600;
      color: #888888;
      min-width: 32px;
      flex-shrink: 0;
    }

    .step-content {
      flex: 1;

      .step-title {
        font-family: 'Montserrat', sans-serif;
        font-size: 24px;
        font-weight: 700;
        color: #5CA4E9;
        margin: 0 0 12px 0;
        line-height: 1.2;
      }

      .step-description {
        font-family: 'Lato', sans-serif;
        font-size: 16px;
        font-weight: 400;
        line-height: 1.6;
        color: #666;
        margin: 0;
      }
    }
  }
}

// Responsive Design
@media (max-width: 1200px) {
  .container {
    padding: 0 32px;
  }

  .content-grid {
    gap: 80px;
  }
}

@media (max-width: 992px) {
  .get-started {
    padding: 100px 0;
  }

  .content-grid {
    grid-template-columns: 1fr;
    gap: 60px;
  }

  .title-section {
    text-align: center;

    .main-title {
      margin-bottom: 40px;
    }
  }

  .process-section {
    gap: 40px;
  }
}

@media (max-width: 768px) {
  .container {
    padding: 0 24px;
  }

  .get-started {
    padding: 80px 0;
  }

  .title-section {
    .cta-section {
      .cta-description {
        font-size: 18px;
      }
    }
  }

  .process-section {
    .process-step {
      gap: 20px;

      .step-content {
        .step-title {
          font-size: 20px;
        }

        .step-description {
          font-size: 15px;
        }
      }
    }
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 16px;
  }

  .get-started {
    padding: 60px 0;
  }

  .process-section {
    gap: 32px;

    .process-step {
      gap: 16px;

      .step-content {
        .step-title {
          font-size: 18px;
          margin-bottom: 8px;
        }
      }
    }
  }
}
</style>