<template>
  <fieldset
    class="st-amount"
    :class="{
      'has-error': hasError,
      'st-amount--is-dark': color === 'dark',
      'st-amount--is-not-empty':
        formattedValue && formattedValue.replace('$', '') > 0
    }"
  >
    <input
      ref="inputRef"
      :type="type"
      :disabled="disabled"
      autocomplete="off"
      :placeholder="placeholder"
      class="st-amount__inner"
      :class="{
        'is-disabled': disabled,
        'is-dirty': formattedValue && formattedValue.replace('$', '') > 0
      }"
      :value="formattedValue"
      @input="inputChange($event.target.value)"
    />
    <div v-if="$slots.default" class="st-icon"><slot /></div>
    <label>{{ hasError ? errorMessages : label }}</label>
  </fieldset>
</template>

<script>
import { ref } from 'vue'
import useCurrencyInput from 'vue-currency-input'
export default {
  name: 'StAmount',
  props: {
    color: {
      type: String,
      required: false,
      default: () => {
        return 'default'
      },
      validator: (value) => {
        return ['default', 'dark'].includes(value)
      }
    },
    icon: {
      type: String,
      required: false,
      default: () => {
        return ''
      }
    },
    modelValue: {
      type: String,
      required: false,
      default: () => {
        return ''
      }
    },
    options: {
      type: Object,
      required: false,
      default: () => {
        return {
          locale: 'en',
          currency: 'USD',
          distractionFree: false,
          valueAsInteger: false,
          useGrouping: true,
          precision: 2,
          allowNegative: false
        }
      }
    },
    disabled: {
      type: Boolean,
      required: false,
      default: () => {
        return false
      }
    },
    type: {
      type: String,
      required: false,
      default: () => {
        return 'text'
      }
    },
    placeholder: {
      type: String,
      required: false,
      default: () => {
        return ''
      }
    },
    hasError: {
      type: Boolean,
      required: false,
      default: () => {
        return false
      }
    },
    errorMessages: {
      type: String,
      required: false,
      default: () => {
        return null
      }
    },
    label: {
      type: String,
      required: false,
      default: () => {
        return 'No label'
      }
    }
  },
  emits: ['update:formattedValue'],
  setup(props, { emit }) {
    let innerValue = ref('')
    const { formattedValue, inputRef } = useCurrencyInput(props.options)
    function inputChange(value) {
      innerValue.value = value
      emit('update:formattedValue', value)
    }

    return {
      inputChange,
      innerValue,
      inputRef,
      formattedValue
    }
  }
}
</script>

<style>
@import '../styles/components/StAmount/StAmount.css';
</style>
