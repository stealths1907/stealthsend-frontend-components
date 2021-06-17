<template>
  <label
    class="st-radio"
    :for="id"
    :class="{ disabled: 'st-radio--is-disabled' }"
  >
    <input
      :id="id"
      :name="name"
      type="radio"
      :class="`st-radio__input st-radio__input-${type}`"
      :checked="isChecked"
      :value="modelValue"
      v-bind="$attrs"
      @change="handleChange"
    />
    <span class="st-radio__label">
      <slot></slot>
    </span>
    <span :class="`st-radio__${type}`"></span>
  </label>
</template>

<script>
import { computed } from 'vue'
export default {
  name: 'StRadio',
  inheritAttrs: false,
  props: {
    disabled: {
      type: Boolean,
      default: false
    },
    type: {
      type: String,
      default: 'round'
    },
    id: {
      type: String,
      required: true
    },
    modelValue: {
      type: String,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    value: {
      type: String,
      required: true
    }
  },
  emits: ['update:modelValue'],
  setup(props, { emit }) {
    function handleChange() {
      emit('update:modelValue', props.value)
    }
    const isChecked = computed(() => props.modelValue === props.value)

    return {
      handleChange,
      isChecked
    }
  }
}
</script>

<style>
@import '../styles/components/StRadio/StRadio.css';
</style>
