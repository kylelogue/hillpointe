<template>
  <section class="hillpointe-difference">
    <div class="container">
      <div class="section-header">
        <span class="section-label">THE HILLPOINTE DIFFERENCE</span>
      </div>
      
      <div class="content-grid">
        <div class="main-statement">
          <h2 class="statement-text">
            In a crowded real estate investment landscape, Hillpointe brings an 
            <span class="accent">owner-operator investment mindset</span> 
            to the institutional world. We utilize a fully vertically integrated platform 
            to create superior risk-adjusted returns.
          </h2>
        </div>
        
        <div class="details-section">
          <div class="detail-block">
            <h3 class="detail-title">Integrated Approach</h3>
            <p class="detail-description">
              Hillpointe is a fully integrated real estate development and investment 
              management firm focused on the development of market rate workforce 
              housing across the Sun Belt.
            </p>
          </div>
          
          <div class="detail-block">
            <h3 class="detail-title">Decades of Experience</h3>
            <p class="detail-description">
              Hillpointe's principals have decades of collective experience in 
              developing, constructing, financing, and managing multifamily assets. 
              The firm's fully integrated approach and ability to deliver real estate 
              assets at a highly attractive cost basis provide a unique competitive 
              advantage versus other real estate investments.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hillpointe-difference {
  padding: 100px 0;
  background: #f8f9fa;
}

.container {
  max-width: 1600px;
  margin: 0 auto;
  padding: 0 45px;
}

.section-header {
  margin-bottom: 60px;

  .section-label {
    font-family: 'Montserrat', sans-serif;
    font-size: 14px;
    font-weight: 600;
    color: #5CA4E9;
    text-transform: uppercase;
    letter-spacing: 1px;
  }
}

.content-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 80px;
}

.main-statement {
  .statement-text {
    font-family: 'Lato', sans-serif;
    font-size: 48px;
    font-weight: 400;
    line-height: 1.3;
    color: #333;
    margin: 0;

    .accent {
      color: #5CA4E9;
      font-weight: 500;
    }
  }
}

.details-section {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;

  .detail-block {
    .detail-title {
      font-family: 'Montserrat', sans-serif;
      font-size: 24px;
      font-weight: 600;
      color: #5CA4E9;
      margin: 0 0 20px 0;
    }

    .detail-description {
      font-family: 'Lato', sans-serif;
      font-size: 18px;
      font-weight: 400;
      line-height: 1.6;
      color: #666;
      margin: 0;
    }
  }
}

@media (max-width: 1200px) {
  .container {
    padding: 0 32px;
  }

  .main-statement {
    .statement-text {
      font-size: 42px;
    }
  }
}

@media (max-width: 992px) {
  .hillpointe-difference {
    padding: 80px 0;
  }

  .content-grid {
    gap: 60px;
  }

  .details-section {
    grid-template-columns: 1fr;
    gap: 60px;
  }

  .main-statement {
    .statement-text {
      font-size: 38px;
    }
  }
}

@media (max-width: 768px) {
  .container {
    padding: 0 24px;
  }

  .hillpointe-difference {
    padding: 60px 0;
  }

  .section-header {
    margin-bottom: 40px;
  }

  .content-grid {
    gap: 40px;
  }

  .main-statement {
    .statement-text {
      font-size: 32px;
      line-height: 1.4;
    }
  }

  .details-section {
    gap: 40px;

    .detail-block {
      .detail-title {
        font-size: 20px;
      }

      .detail-description {
        font-size: 16px;
      }
    }
  }
}

@media (max-width: 480px) {
  .container {
    padding: 0 16px;
  }

  .main-statement {
    .statement-text {
      font-size: 28px;
    }
  }

  .details-section {
    .detail-block {
      .detail-title {
        font-size: 18px;
        margin-bottom: 16px;
      }

      .detail-description {
        font-size: 15px;
      }
    }
  }
}
</style>