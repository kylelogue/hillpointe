<script lang="ts" setup>
import { ref } from 'vue';

interface LoanProduct {
  id: string;
  title: string;
  unitInfo: string;
  additionalInfo?: string;
  loanAmount: string;
  maxLoanToValue: string;
  termLength: string;
  additional: string;
  tabNumber: string;
}

const activeTab = ref('single-family');

const loanProducts: LoanProduct[] = [
  {
    id: 'single-family',
    title: 'SINGLE FAMILY',
    unitInfo: '1-4 Unit / Townhomes / Condos',
    loanAmount: '$300,000 - $3,500,000',
    maxLoanToValue: '80% LTV',
    termLength: '30 Year Fixed',
    additional: 'Interest Only Option',
    tabNumber: '01',
  },
  {
    id: 'short-term-rentals',
    title: 'SHORT TERM RENTALS',
    unitInfo: '1-4 Unit / Townhomes / Condos',
    loanAmount: '$300,000 - $3,500,000',
    maxLoanToValue: '75% LTV',
    termLength: '30 Year Fixed',
    additional: 'Interest Only Option',
    tabNumber: '02',
  },
  {
    id: 'multi-family',
    title: 'MULTI FAMILY',
    unitInfo: '5+ Units / Mixed Use',
    loanAmount: '$300,000 - $10,000,000',
    maxLoanToValue: '75% LTV',
    termLength: '30 Year Fixed',
    additional: 'Interest Only Option',
    tabNumber: '03',
  },
  {
    id: 'cross-portfolio',
    title: 'CROSS PORTFOLIO',
    unitInfo: '1-4 Units / Townhomes / Condos',
    additionalInfo: '5-20 Unit Properties Allowed',
    loanAmount: '$1,000,000 - $15,000,000',
    maxLoanToValue: '75% LTV',
    termLength: '30 Year Fixed',
    additional: 'Interest Only Option',
    tabNumber: '04',
  }, 
];

const setActiveTab = (tabId: string) => {
  activeTab.value = tabId;
};

const getActiveProduct = () => {
  return loanProducts.find(product => product.id === activeTab.value) || loanProducts[0];
};
</script>

<template>
  <div class="loan-tabs">

    <div class="tab-navigation">
      <button
        v-for="product in loanProducts"
        :key="product.id"
        :class="['tab-button', { active: activeTab === product.id }]"
        @click="setActiveTab(product.id)"
      >
        {{ product.title }}
      </button>
    </div>

    <div class="tab-content">
      <div class="content-header">
        <div class="title-section">
          <h2 class="product-title">{{ getActiveProduct().title }}</h2>
          <p class="unit-info">{{ getActiveProduct().unitInfo }}</p>
          <p
            v-if="getActiveProduct().additionalInfo"
            class="additional-info"
          >
            {{ getActiveProduct().additionalInfo }}
          </p>
        </div>
        <div class="tab-number">{{ getActiveProduct().tabNumber }}</div>
      </div>

      <div class="content-details">
        <div class="detail-row">
          <div class="detail-item">
            <h4 class="detail-label">Loan Amount</h4>
            <p class="detail-value">{{ getActiveProduct().loanAmount }}</p>
          </div>
          <div class="detail-item">
            <h4 class="detail-label">Max Loan to Value</h4>
            <p class="detail-value">{{ getActiveProduct().maxLoanToValue }}</p>
          </div>
        </div>

        <div class="detail-row">
          <div class="detail-item">
            <h4 class="detail-label">Term Length</h4>
            <p class="detail-value">{{ getActiveProduct().termLength }}</p>
          </div>
          <div class="detail-item">
            <h4 class="detail-label">Additional</h4>
            <p class="detail-value">{{ getActiveProduct().additional }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.loan-tabs {
  background: white;
  border-radius: 0;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  max-width: 700px;
  width: 100%;
}

.tab-navigation {
  display: flex;
  background: transparent;

  .tab-button {
    flex: 1;
    padding: 20px 16px;
    border: none;
    background: #5CA4E9;
    color: white;
    font-family: 'Montserrat', sans-serif;
    font-size: 13px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    cursor: pointer;
    transition: all 0.2s ease;
    position: relative;

    &:not(:last-child) {
      border-right: 1px solid rgba(255, 255, 255, 0.2);
    }

    &:hover {
      background: #357ABD;
    }

    &.active {
      background: white;
      color: #333;
    }
  }
}

.tab-content {
  padding: 40px 32px;
  background: white;
  min-height: 300px;

  .content-header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 40px;

    .title-section {
      flex: 1;

      .product-title {
        font-family: 'Montserrat', sans-serif;
        font-size: 48px;
        font-weight: 900;
        color: #333;
        margin: 0 0 16px 0;
        line-height: 0.9;
        text-transform: uppercase;
        letter-spacing: -2px;
      }

      .unit-info {
        font-family: 'Lato', sans-serif;
        font-size: 18px;
        color: #666;
        margin: 0 0 8px 0;
        font-weight: 400;
      }

      .additional-info {
        font-family: 'Lato', sans-serif;
        font-size: 16px;
        color: #888;
        margin: 0;
        font-weight: 400;
      }
    }

    .tab-number {
      font-family: 'Montserrat', sans-serif;
      font-size: 72px;
      font-weight: 200;
      color: #999999;
      line-height: 1;
      margin-top: -8px;
    }
  }

  .content-details {
    .detail-row {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
      margin-bottom: 32px;

      &:last-child {
        margin-bottom: 0;
      }

      .detail-item {
        .detail-label {
          font-family: 'Montserrat', sans-serif;
          font-size: 16px;
          font-weight: 700;
          color: #333;
          margin: 0 0 8px 0;
          text-transform: none;
          letter-spacing: 0;
        }

        .detail-value {
          font-family: 'Lato', sans-serif;
          font-size: 18px;
          color: #666;
          margin: 0;
          font-weight: 400;
        }
      }
    }
  }
}

@media (max-width: 768px) {
  .loan-tabs {
    max-width: 100%;
  }

  .tab-navigation {
    .tab-button {
      font-size: 11px;
      padding: 16px 12px;
    }
  }

  .tab-content {
    padding: 32px 24px;

    .content-header {
      .title-section {
        .product-title {
          font-size: 36px;
        }
      }

      .tab-number {
        font-size: 56px;
      }
    }
  }
}
</style>