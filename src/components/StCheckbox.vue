<template>
  <label class="st-checkbox">
    <span class="st-checkbox__label">
      <slot></slot>
    </span>
    <input
      type="checkbox"
      class="st-checkbox__input"
      :value="label"
      :checked="modelValue"
      @input="handleInput"
    />
    <span class="st-checkbox__checkmark">
      <span class="check"></span>
    </span>
  </label>
</template>

<script>
export default {
  name: 'StCheckbox',
  props: {
    modelValue: {
      type: [String, Boolean],
      required: true
    },
    label: {
      type: [String, Boolean],
      required: false,
      default: false
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

<style>
@import '../styles/components/StCheckbox/StCheckbox.css';
</style>
