<script lang="ts" setup>
interface Props {
  text: string
  variant?: 'blue' | 'dark' | 'light'
  size?: 'small' | 'medium' | 'large'
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'blue',
  size: 'medium'
})
</script>

<template>
  <button 
    class="styled-button" 
    :class="[`variant-${props.variant}`, `size-${props.size}`]"
  >
    {{ text }}
  </button>
</template>

<style lang="scss" scoped>
.styled-button {
  border: none;
  // border-radius: 25px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.2s ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-family: inherit;

  // Size variants
  &.size-small {
    padding: 8px 20px;
    font-size: 14px;
  }

  &.size-medium {
    padding: 12px 24px;
    font-size: 16px;
  }

  &.size-large {
    padding: 16px 32px;
    font-size: 18px;
  }

  // Color variants
  &.variant-blue {
    background: #357ABD;
    color: white;

    &:hover {
      transform: translateY(-1px);
    }
  }

  &.variant-dark {
    background-color: #333333;
    color: white;

    &:hover {
      background-color: #222222;
      transform: translateY(-1px);
    }
  }

  &.variant-light {
    background-color: white;
    color: #333333;
    border: 1px solid #e0e0e0;

    &:hover {
      background-color: #f5f5f5;
      transform: translateY(-1px);
    }
  }

  &:active {
    transform: translateY(0);
  }
}
</style>