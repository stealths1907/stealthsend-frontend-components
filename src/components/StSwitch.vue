<template>
  <label :class="`st-switch--${theme}`">
    <input
      type="checkbox"
      :class="`st-switch__input ${type}`"
      :value="label"
      :checked="modelValue"
      @input="handleInput"
    />
    <div v-if="type === 'simple'" class="st-switch--simple">
      <div class="st-switch__bullet" />
    </div>
    <div v-if="type === 'thunder'" class="st-switch--thunder">
      <div class="st-switch--thunder-icon">
        <svg
          width="9"
          height="12"
          viewBox="0 0 9 12"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path d="M5.5 5L6.5 0L0.5 7H3.5L2.5 12L8.5 5H5.5Z" fill="#E0D3FC" />
        </svg>
      </div>
    </div>
    <span class="st-switch__label">
      <slot />
    </span>
  </label>
</template>

<script>
export default {
  name: 'StSwitch',
  props: {
    modelValue: {
      type: [String, Boolean],
      required: true
    },
    label: {
      type: [String, Boolean],
      required: false,
      default: false
    },
    type: {
      type: String,
      required: true,
      default: 'simple',
      validator: (value) => {
        return ['simple', 'thunder'].includes(value)
      }
    },
    theme: {
      type: String,
      required: true,
      default: 'light',
      validator: (value) => {
        return ['light', 'dark'].includes(value)
      }
    }
  },
  emits: ['update:modelValue'],
  setup(props, ctx) {
    function handleInput(event) {
      let isChecked = event.target.checked
      ctx.emit('update:modelValue', isChecked)
    }

    return {
      handleInput
    }
  }
}
</script>

<style scoped>
.st-switch--light,
.st-switch--dark {
  position: relative;
  display: flex;
  align-items: center;
  width: fit-content;
}
.st-switch--dark .st-switch--thunder-icon {
  background-color: var(--marine500);
}
.st-switch--light .st-switch__label {
  color: var(--text);
}
.st-switch--dark .st-switch__label {
  color: var(--white);
}
.st-switch__input.thunder {
  position: absolute;
  margin: 0;
  width: 60px;
  height: 32px;
  opacity: 0;
}
svg path {
  transition: 0.3s;
}
.st-switch__input:checked ~ .st-switch--thunder .st-switch--thunder-icon {
  transform: translateX(27px);
  background-color: var(--grey50);
}
.st-switch__input:checked
  ~ .st-switch--thunder
  .st-switch--thunder-icon
  svg
  path {
  fill: var(--marine500);
}
.st-switch__input:checked ~ .st-switch--simple .st-switch__bullet {
  transform: translateX(19px);
  background-color: var(--marine500);
}
.st-switch--thunder {
  position: relative;
  width: 60px;
  height: 32px;
  border: 1.5px solid var(--grey200);
  border-radius: 18px;
}
.st-switch--thunder-icon {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 24px;
  height: 24px;
  border-radius: 24px;
  background-color: var(--marine800);
  position: absolute;
  left: 4px;
  top: 4px;
  transition: 0.3s;
}
.st-switch__input.simple {
  position: absolute;
  margin: 0;
  width: 46px;
  height: 24px;
  opacity: 0;
}
.st-switch--simple {
  position: relative;
  width: 46px;
  height: 24px;
  border: 1.5px solid var(--grey200);
  border-radius: 19px;
  box-sizing: border-box;
}
.st-switch--simple .st-switch__bullet {
  width: 19px;
  height: 18px;
  border-radius: 18px;
  background-color: var(--grey100);
  position: absolute;
  left: 3px;
  top: 1px;
  transition: 0.3s;
}
.st-switch__label {
  font-family: var(--secondary-font);
  font-size: 12px;
  line-height: 24px;
  letter-spacing: 0.12px;
  margin-left: 24px;
}
</style>
