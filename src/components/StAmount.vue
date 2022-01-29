<template>
  <div class="st-input">
    <input
      ref="inputRef"
      :type="type"
      :disabled="disabled"
      :placeholder="placeholder"
      autocomplete="off"
      class="st-input__inner"
      :value="value"
    />
    <div v-if="$slots.default" class="st-icon"><slot /></div>
  </div>
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
      type: Number,
      required: false,
      default: () => {
        return 0
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
        return this.formattedValue
      },
      set(value) {
        this.$emit('update:formattedValue', value)
      }
    }
  }
}
</script>

<style>
@import '../styles/components/StInput/StInput.css';
</style>
