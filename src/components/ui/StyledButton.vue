<script lang="ts" setup>
interface Props {
  text: string
  color?: 'blue' | 'dark' | 'light'
  size?: 'small' | 'medium' | 'large'
  rounded?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  color: 'blue',
  size: 'medium',
  rounded: false,
});
</script>

<template>
  <button 
    class="styled-button" 
    :class="[`color-${props.color}`, `size-${props.size}`, `${ props.rounded ? 'rounded' : ''}`]"
  >
    {{ text }}
  </button>
</template>

<style lang="scss" scoped>
.styled-button {
  border: none;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-family: inherit;

  &.size-medium {
    padding: 12px 24px;
    font-size: 18px;
  }

  &.size-large {
    padding: 32px 48px;
    font-size: 48px;
  }


  &.color-blue {
    background: #357ABD;
    color: #FFFFFF;

    &:hover {
      transform: translateY(-2px);
    }
  }

  &.color-dark {
    background-color: #333333;
    color: white;

    &:hover {
      transform: translateY(-2px);
    }
  }

  &.color-light {
    background-color: #FFFFFF;
    color: #333333;

    &:hover {
      transform: translateY(-2px);
    }
  }

  &.rounded {
    border-radius: 25px;
  }

  &:active {
    transform: translateY(0);
  }
}
</style>