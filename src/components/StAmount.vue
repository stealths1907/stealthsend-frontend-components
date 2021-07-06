<template>
  <fieldset
    class="st-amount"
    :class="{
      'has-error': hasError,
      'st-amount--is-not-empty':
        (formattedValue && formattedValue.replace('$', '') > 0) ||
        (formattedValue && formattedValue.replace('XST', '') > 0)
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
        'is-dirty':
          (formattedValue && Number(formattedValue.replace('$', '')) > 0) ||
          (formattedValue && Number(formattedValue.replace('XST', '')) > 0)
      }"
      :value="value"
    />
    <div v-if="$slots.default" class="st-icon"><slot /></div>
  </fieldset>
</template>

<script>
import { ref } from 'vue'
import useCurrencyInput from 'vue-currency-input'
export default {
  name: 'StAmount',
  props: {
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
    }
  },
  emits: ['update:formattedValue'],
  setup(props) {
    let innerValue = ref('')
    const { formattedValue, inputRef } = useCurrencyInput(props.options)
    return {
      innerValue,
      inputRef,
      formattedValue
    }
  },
    computed: {
    value: {
      get() {
        return this.formattedValue;
      },
      set(value) {
        this.$emit("update:formattedValue", value);
      }
    }
  }
}
</script>

<style>
@import '../styles/components/StAmount/StAmount.css';
</style>
